# Istanbul Reporter AWS Cloudwatch Metrics

This is a custom [istanbuljs](https://github.com/istanbuljs/istanbuljs) reporter to generate coverage metrics to AWS Cloudwatch Metrics.

## Installing

In your project:
```
npm install -i istanbul-reporter-aws-cloudwatch-metrics --save-dev
```

Then run `nyc` with this custom reporter via the command line:

```
nyc --reporter=istanbul-reporter-aws-cloudwatch-metrics mocha
```

Or, change your npm scripts for your project in package.json:

```json
  (...)
  "scripts": {
    "test": "nyc --reporter=istanbul-reporter-aws-cloudwatch-metrics mocha"
  },
  (...)
```

## Getting Started

After running nyc and having your coverage results you'll have a `coverage/metric_data.json` file
ready to be published to AWS Cloudwatch Metrics with:

```
aws cloudwatch put-metric-data --namespace "MyTestNamespace" --metric-data file://./coverage/metric_data.json
```

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process
for submitting pull requests to us.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
