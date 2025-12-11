FROM mcr.microsoft.com/dotnet/sdk:9.0-alpine AS build-stage
WORKDIR /build
COPY . .
RUN dotnet publish

FROM mcr.microsoft.com/dotnet/aspnet:9.0-alpine
WORKDIR /app
COPY --from=build-stage /build/bin/Release/net9.0/publish .
ENTRYPOINT ["/app/Deo.Backend"]