# Web site for ChoixDeVie.fr
Created with Orchard Core (Asp.Net Core 3)

# LifeChoices project
## Functional
This project aimed to give all the technical features for a coaching platform, in C# .Net Core (.Net Core 3.1, before .Net 5+).
The main priority is the protection of personal data and privacy:
- open-source
- could be used on cloud (Azure, AWS...) or on premise
- security concerns about personal data

## Technical
### Main features
Open-source C# .Net Core framework for:
- a web app: LifeChoices.Web (Asp.Net Core 3.1+, with Orchard Core)
- a mobile/tablet app: LifeChoices.App (Xamarin 4.4+)
### Additional features
- to the web app: create a microservice architecture, with the web site (using Dapr?), and a big data service (gRPC) for IoT devices
- to the mobile app: add desktop compatibility (macOs, Windows 10...)
- add smartband/IoT devices compatibility: get detailed personal informations
