# aws-lambda-serverless-fsharp
AWS lambda template for FSharp on netcore2.0 using Serverless framework

## Credits
This template and doc are based on the Fsharp template provided by [Serverless](https://github.com/serverless/serverless/tree/master/docs/providers/aws/examples/hello-world/fsharp).

It mainly adds:
- Paket for package management
- netcore2.0 support

## What is it?
This is a simple netcore2.0 project aiming at make deploy of compiled FSharp apps easy like 1-2-3.
It will take just a few minutes to install the tools and have your netcore2.0 app deployed to AWS Lambda.

## Prerequisites
1 - [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/installing.html) is installed

2 - [AWS credentials](https://docs.aws.amazon.com/fr_fr/cli/latest/userguide/cli-chap-getting-started.html) have been set with `aws configure`

3 - [Serverless](https://serverless.com/) is installed with `npm install serverless -g`

## 1. Init Paket
1 - Update Paket: `.paket/paket.bootstrapper.exe`

2 - Init Paket: `.paket/paket.exe init`

## 2. Build using .NET Core 2.X CLI tools and create zip package

```
# Linux or Mac OS
./build.sh
```

```
# Windows PowerShell
./build.cmd
```

## 3. Deploy

```
sls deploy
```

This will deploy your function to AWS Lambda based on the settings in `serverless.yml`.

## 4. Invoke deployed function

```
sls invoke -f hello
```

Invoke deployed function with command `invoke` and `--function` or shorthand `-f`.

In your terminal window you should see the response from AWS Lambda.

```bash
{
    "Message": "Your function executed successfully!",
    "Request": {
        "Key1": null,
        "Key2": null,
        "Key3": null
    }
}
```

Congrats you have deployed and ran your Hello World function!
