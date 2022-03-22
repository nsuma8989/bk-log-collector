# Buildkite Elastic CI Stack Log Collector
A bash script intended to make it easier to collect logs for troubleshooting Buildkite agents running on the [Buildkite Elastic CI Stack](https://github.com/buildkite/elastic-ci-stack-for-aws). If you need assistance from Buildkite support, please run this script and send the logs to support@buildkite.com.

## Setup

Clone the repo:

```bash
git clone https://github.com/jeremybumsted/bk-log-collector.git
```

Ensure you have the configured the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

It is recommended you use a tool like [aws-vault](https://github.com/99designs/aws-vault) to manage your credentials and sessions.


## Usage

Currently, the script requires an Autoscaling Group Name and an instance ID:

```bash
./bk-log-collector -s <ASG-Group-Name> -i <Instance-ID>
```

For more details on the input parameters:

```bash
./bk-log-collector -h
```

This will collect logs from the following locations in CloudWatch and store them in a zip file in `/tmp/buildkite-logs-[date].zip`:

```
/buildkite/buildkite-agent
/buildkite/system
/buildkite/lifecycled
/buildkite/docker-daemon
```





