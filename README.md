[![Build Status](https://travis-ci.org/ibm-cloud-solutions/cloudbot.svg?branch=master)](https://travis-ci.org/ibm-cloud-solutions/cloudbot)
[![Dependency Status](https://dependencyci.com/github/ibm-cloud-solutions/cloudbot/badge)](https://dependencyci.com/github/ibm-cloud-solutions/cloudbot)
[![npm](https://img.shields.io/npm/v/cloudbot.svg?maxAge=2592000)](https://www.npmjs.com/package/cloudbot)

# cloudbot

- A robot may not injure a human being or, through inaction, allow a human being to come to harm.
- A robot must obey orders given it by human beings except where such orders would conflict with the First Law.
- A robot must protect its own existence as long as such protection does not conflict with the First or Second Law.

## Getting Started

  * [Setup](#setup)
  * [Usage](#usage)
  * [Docs & Community](#community)
  * [Demos](#demos)
  * [Deploying to IBM Bluemix](#deploying-to-ibm-bluemix)
  * [Enhancing](#enhancing)
  * [License](#license)
  * [Contribute](#contribute)

## Setup

Setting up your bot is simple. Install the dependencies:

```
npm install
```

## Usage

With the dependencies installed, starting cloudbot requires the environment variables `HUBOT_NAME` and `ADAPTER` be set. The booting sequence will begin with

```
npm start
```

Certain scripts may require other environment variables to be set. Check out the documentation for each of these scripts, as it will provide the proper information.

## Included Scripts
* [hubot-diagnostics](https://github.com/hubot-scripts/hubot-diagnostics)
* [hubot-emit-tweeter](https://github.com/ibm-cloud-solutions/hubot-emit-tweeter)
* [hubot-environment](https://github.com/ibm-cloud-solutions/hubot-environment)
* [hubot-help](https://github.com/hubot-scripts/hubot-help)
* [hubot-pugme](https://github.com/hubot-scripts/hubot-pugme)
* [hubot-redis-brain](https://github.com/hubot-scripts/hubot-redis-brain)
* [hubot-shipit](https://github.com/hubot-scripts/hubot-shipit)
* [hubot-ibmcloud-alerts](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-alerts)
* [hubot-ibmcloud-app-management](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-app-management)
* [hubot-ibmcloud-auth](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-auth)
* [hubot-ibmcloud-cloudant](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-cloudant)
* [hubot-ibmcloud-container-management](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-container-management)
* [hubot-ibmcloud-deploy](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-deploy)
* [hubot-ibmcloud-formatter](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-formatter)
* [hubot-ibmcloud-github-issues](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-github-issues)
* [hubot-ibmcloud-logger](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-logger)
* [hubot-ibmcloud-nlc](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-nlc)
* [hubot-ibmcloud-objectstorage](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-objectstorage)
* [hubot-ibmcloud-openwhisk](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-openwhisk)
* [hubot-ibmcloud-redis](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-redis)
* [hubot-ibmcloud-service-management](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-service-management)
* [hubot-ibmcloud-service-status](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-service-status)
* [hubot-ibmcloud-service-suggest](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-service-suggest)
* [hubot-ibmcloud-space-management](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-space-management)
* [hubot-ibmcloud-translate](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-translate)
* [hubot-ibmcloud-twitter](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-twitter)
* [hubot-ibmcloud-virtualserver](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-virtualserver)
* [hubot-ibmcloud-weather](https://github.com/ibm-cloud-solutions/hubot-ibmcloud-weather)
* [hubot-versions](https://github.com/ibm-cloud-solutions/hubot-versions)

## Community
* [Website and Documentation](https://developer.ibm.com/open/cloudbot/)
* [Slack](https://dwopen.slack.com/messages/cognitive-cloudbot/) - [(join)](https://developer.ibm.com/open/slack-request)
* [Stack Overflow](http://stackoverflow.com/search?q=hubot)
* [DW Answers](https://developer.ibm.com/answers/smartspace/open/)

## Demos

Please check out our [YouTube videos](https://www.youtube.com/channel/UCr_27wo89y23LoHLG_sKrqw) to learn more about cloudbot and how quickly your DevOps team can embrace our bot capabilities across a variety of integrations.

## Deploying to IBM Bluemix

Before deploying your custom cloudbot to IBM Bluemix, you need to create a manifest.yml file with the properties you need for specific scripts. There is a sample manifest file with minimum required configuration, follow these instructions to customize and deploy a cloudbot to your IBM Bluemix account:

1. Clone this repo and cd to the the folder where you have this repo.

2. If you have not already logged into IBM Bluemix, use the following commands to login:
```
cf api https://api.ng.bluemix.net/
cf login
```
3. Create Cloudant and Watson Natural Language Classifier services.
```
cf cs cloudantNoSQLDB Shared cloudbot-cloudant
cf cs natural_language_classifier standard cloudbot-nlc
```
4. Copy the manifext_sample.yml to manifest.yml and update the properties in manifest file, based on the scripts you need for your bot.

5. Deploy your bot to IBM Bluemix.
```
cf push -f manifest.yml
```
6. It will take several minutes to deploy the node application to IBM Bluemix. Once your application is started, you should be able to interact with the newly deployed bot from your Slack account.

## Enhancing

More functionality can be added to cloudbot; it knows no limits. Add the script to the dependency list in `package.json`, and reference that script in the array of `external-scripts.json`.

## License

See [LICENSE.txt](https://github.com/ibm-cloud-solutions/cloudbot/blob/master/LICENSE.txt) for license information.

## Contribute

Please check out our [Contributing Guidelines](https://github.com/ibm-cloud-solutions/cloudbot/blob/master/CONTRIBUTING.md) for detailed information on how you can lend a hand.
