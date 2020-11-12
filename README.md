# Alert Manager Silence Scheduler

This utility is... and does...

## Development

There's a simple `Makefile` provided which exposes the following functions:
*   `build`: builds the go binary
*   `test`: runs the unit tests
*   `integration-test`: launches a local Alert Manager docker container and tests the utility
*   `start-alert-manager`: starts an Alert Manager docker container in the background
*   `stop-alert-manager`: removes any background Alert Manager docker processes
*   `zip`: produces a tagged zip archive
*   `clean`: removes all local build artifacts from disk 

## Deployment

## Usage

Takes a JSON event...

### Example Input

    [
        {
            "Service": "ExampleService",
            "StartScheduleCron": "0 3 * * 0",
            "EndScheduleCron": "0 4 * * 0",
            "Matchers": [
                {
                    "IsRegex": false,
                    "Name": "environment",
                    "Value": "test"
                },
                {
                    "IsRegex": false,
                    "Name": "alertname",
                    "Value": "HostDown"
                }
            ]
        },
        {
            "Service": "ExampleServiceTwo",
            "StartScheduleCron": "0 8 * * 0",
            "EndScheduleCron": "0 9 * * 0",
            "Matchers": [
                {
                    "IsRegex": false,
                    "Name": "environment",
                    "Value": "prod"
                },
                {
                    "IsRegex": false,
                    "Name": "alertname",
                    "Value": "LambdaError"
                }
            ]
        }
    ]