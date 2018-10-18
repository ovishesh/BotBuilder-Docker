FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# copy csproj and restore as distinct layers
COPY ./src/*.csproj .
RUN dotnet restore

# copy everything else and build app
COPY ./src/. .
WORKDIR /app
RUN dotnet publish -c Release -o out


FROM microsoft/dotnet:2.1-aspnetcore-runtime AS runtime
WORKDIR /app
# COPY ./src/*.bot ./
COPY --from=build /app/out ./
ENTRYPOINT ["dotnet", "EchoBotWithCounter.dll"]