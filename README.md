# AWS Ffmpeg Lambda Layer
[![serverless](http://public.serverless.com/badges/v3.svg)](http://www.serverless.com)

### Statically compiled Ffmpeg binary with serverless file to setup a lambda layer.


## Usage
Clone the repo and unzip the binary which is located in the ```bin``` folder.

Run ```sls deploy -v``` to deploy layer with Serverless (you need to have Serverless installed and setup for this...).

You can then reference the layer in your main Serverless .yml file like so:

```
functions:
  myLambda:
    handler: handlers/myLambda.run
    layers:
      - Fn::ImportValue: FfmpegLambdaLayer
```
```FfmpegLambdaLayer``` is specified in the layers .yml file, but you can call it what you want. Layer will be on its own CloudFormation stack, but you can still reference it with the exported name value in the Serverless setup here.