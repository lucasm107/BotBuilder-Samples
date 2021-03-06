# declarative-bot

Bot Framework v4 echo bot sample using declarative form of [adaptive dialogs (PREVIEW)][1] and Orchestrator (PREVIEW)


## Prerequisites

This sample **requires** prerequisites in order to run.
- Install latest supported version of [Visual C++](https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads)
- Install latest [Bot Framework Emulator](https://github.com/microsoft/BotFramework-Emulator/releases)
- [Node.js](https://nodejs.org) version 10.14 or higher
    ```bash
    > node --version
    ```
- Install BF CLI with Orchestrator plugin
    - Install bf cli 
    ```bash
    > npm i -g @microsoft/botframework-cli
    ```
    - Install bf orchestrator
    ```bash
    > bf plugins:install @microsoft/bf-orchestrator-cli@beta
    ```
    - Make sure bf orchestrator command is working and shows all available orchestrator commands
    ```bash
    > bf orchestrator
    ```
    
## To try this bot sample

- Clone the repository
    ```bash
    > git clone https://github.com/microsoft/botbuilder-samples.git
    ```
- CD experimental/orchestrator/javascript_nodejs/03.declarative-bot
    ```bash
    > cd experimental/orchestrator/javascript_nodejs/03.declarative-bot
    ```
- Configure Orchestrator: Download NLR model
    - You can view list of available models using this command.  Copy Version Id value from latest model and use it for --versionId parameter the get command below.
    ```bash
    > bf orchestrator:nlr:list
    ```
    - Download the NLR model
    ```bash
    > mkdir model
    > bf orchestrator:nlr:get --versionId <version id> --out ./model --verbose
    ```
    - Build the Orchestrator snapshot
    ```bash
    > mkdir generated
    > bf orchestrator:build --dialog --in ./dialogs --out ./generated --model ./model
    ```
    - Update orchestrator modelPath and snapshotPath information in `./.env`
- Install modules

    ```bash
    > npm install
    ```
- Start the bot

    ```bash
    > npm start
    ```

## Connect to the bot using Bot Framework Emulator

- Launch Bot Framework Emulator
- File -> Open Bot
- Enter a Bot URL of `http://localhost:3978/api/messages`

## Further reading
- [Bot Framework Documentation](https://docs.botframework.com)
- [Bot Basics](https://docs.microsoft.com/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Activity processing](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [Azure Bot Service Introduction](https://docs.microsoft.com/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Azure Bot Service Documentation](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)
- [.NET Core CLI tools](https://docs.microsoft.com/en-us/dotnet/core/tools/?tabs=netcore2x)
- [Azure CLI](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)
- [Azure Portal](https://portal.azure.com)
- [Channels and Bot Connector Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)

[1]:https://aka.ms/adaptive-dialogs
[2]:https://aka.ms/language-generation