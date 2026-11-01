# pac-PolicyDryRun
Runs one local check: whether a resource named by a `resource_must_exist` rule in a policy file exists in an environment file. The policy file holds a `resource_must_exist` object with a `type` and a `name`; the environment file lists resources under that type, and the check passes when one of them has the matching name. Both files are local YAML or JSON files the operator supplies. Nothing is fetched from AWS, Azure, or any other service, no cloud SDK is used, and no other policy content is evaluated: there is no conflict detection and no prediction of consequences. A policy with no `resource_must_exist` rule runs zero checks and reports not checked at exit 1, and a found violation exits 1; only a check that ran and passed exits 0. The tool writes nothing and changes nothing. - Focused on Tools to validate infrastructure-as-code (IaC) definitions (e.g., Terraform, CloudFormation) and configuration files against predefined security policies. Automates security checks during infrastructure development and deployment.

## Install
`git clone https://github.com/ShadowGuardAI/pac-policydryrun`

## Usage
`python3 main.py [params]`

## Parameters
- `-h`: Show help message and exit
- `--policy-file`: Path to the policy definition file (YAML or JSON).
- `--environment-file`: Path to the environment definition file (YAML or JSON) representing the current infrastructure.
- `--format`: Format of the policy and environment files (yaml or json). Default: yaml
- `--schema-file`: Path to the JSON schema file for validating the policy definition.
- `--log-level`: Set the logging level. Default: INFO

## License
Copyright (c) ShadowGuardAI
