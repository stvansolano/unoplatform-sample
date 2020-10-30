FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-buster-slim AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/core/sdk:2.2-buster AS build
WORKDIR /src

COPY [".", "."]
RUN dotnet restore "HelloWorld.Wasm/HelloWorld.Wasm.csproj"

RUN dotnet build "HelloWorld.Wasm/HelloWorld.Wasm.csproj" -c Release -o /app/build 

FROM build AS publish
RUN dotnet publish "HelloWorld.Wasm/HelloWorld.Wasm.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
RUN ls
ENTRYPOINT ["dotnet", "HelloWorld.Wasm.dll"]

# docker run -p 5000:80 unoplatformsample:latest