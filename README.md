# Cloud-bill

Estimate environmental impact of your AWS resources by combining an AWS cloud usage report with data from Boavizta API.

General idea is to use _cold_ data (csv file) retrieved manually from AWS cold explorer (see https://docs.aws.amazon.com/cost-management/latest/userguide/ce-saving.html).
It provides hours of usage for different instances types, and we can use it to query Boa API.

⚠ Warning: _Work In Progress_ code produced during Boavizta Hackaton #4 (https://boavizta.org/en).

## Usage

```sh
# Set you aws profile (you may need aws cli install first)
export AWS_PROFILE=my-custom-profile-name
cd src/bills
# Run the analysis on the provide sample.csv file
python main.py -i sample.csv
```

## Source

Relevant source is in `/src/bill` 

## Other sample code

These samples were produced during Boavizta Hackaton #4 (https://boavizta.org/en) and mainly left unmaintained.

We keep them because they may provide example about how we can query Cloudwath and Boavizta API.

### Query AWS account

See some examples of querying aws api in `src/sample_code/instance-usage/python print-instance-usage.py`.

## Query account to combine usage with impacts

### Principle

1. Query AWS apis to list all instances of the account and retrieve average CPU utilization
2. Use theses results to query Boavizta API to get impacts

### Usage

Authenticate against aws using a specific profile with `export AWS_PROFILE=my-custom-profile-name`.

```bash
cd src/sample_code/instances-impacts-from-cloudwatch
python main.py
```

```bash
cd src/sample_code/instances-impacts-from-cloudwatch
python test_main.py
```
