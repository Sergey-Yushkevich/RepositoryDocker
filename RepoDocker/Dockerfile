FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o /publish

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS runtime
WORKDIR /app
COPY --from=build /publish .
ENTRYPOINT [ "dotnet", "RepoDocker.dll" ]
#WORKDIR /app
#COPY . .
#RUN dotnet build
#ENTRYPOINT [ "dontet", "run"]