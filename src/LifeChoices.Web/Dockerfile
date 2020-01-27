#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.
# Compilation of Docker image:
#> cd LifeChoices.Web
#> docker build -t choixdevie -f ./src/LifeChoices.Web/Dockerfile .

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ../../NuGet.config ./
COPY ["src/LifeChoices.Web/LifeChoices.Web.csproj", "src/LifeChoices.Web/"]
RUN dotnet restore "src/LifeChoices.Web/LifeChoices.Web.csproj"
COPY . .
WORKDIR "/src/src/LifeChoices.Web"
RUN dotnet build "LifeChoices.Web.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "LifeChoices.Web.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "DevLabAlsace.LifeChoices.Web.dll"]