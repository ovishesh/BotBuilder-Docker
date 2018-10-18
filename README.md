# BotBuilder v4 Echobot with Docker
This repository shows how to get a bot built with [BotBuilder v4 SDK](https://github.com/Microsoft/BotBuilder) running in a docker container. It uses the [Echo With Counter](https://github.com/Microsoft/BotBuilder-Samples/tree/master/samples/csharp_dotnetcore/02.echo-with-counter) sample.

**Note:** Only `aspdotnetcore2.1 ` sample available at the moment, others coming soon.

## Steps
1. Clone the repo - `git clone https://github.com/ovishesh/BotBuilder-Docker`
1. Open a `Command Prompt` and change your working directory to `dotnet`
1. Build the image `docker build -t echobotwithdocker .`
1. Run the image `docker run --name echobot --rm -it -p 8000:80 echobotwithdocker`
1. Open the `BotConfiguration.bot` file with the new [Bot Framework Emulator (V4 PREVIEW)](https://github.com/Microsoft/BotFramework-Emulator) or Navigate to `http://localhost:8000/` to view the default web page `src/wwwroot/default.htm`
1. `Ctrl+C` to shut the container


## References
- [Dotnet Docker Samples for ASPNET Apps](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp)
- [BotBuilder-Samples](https://github.com/Microsoft/BotBuilder-Samples/tree/master/samples/csharp_dotnetcore/02.echo-with-counter)
- [BotBuilder-dotnet SDK](https://github.com/microsoft/botbuilder-dotnet)
- [Migrate from ASP.NET Core 2.0 to 2.1](https://docs.microsoft.com/en-us/aspnet/core/migration/20_21?view=aspnetcore-2.1)