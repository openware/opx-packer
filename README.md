# OPX Packer modules

This repository contains all Packer files used for OPX-based deployments

## Base images

The list of base Debian 10 AMI's per region is as follows:
|Region| AMI|
|---|---|
|af-south-1	| ami-0db145f13ff800d7b|
|ap-east-1	| ami-0b94935e67a9d50ff|
|ap-northeast-1	| ami-0ac97798ccf296e02|
|ap-northeast-2	| ami-0b4a713d12660d96c|
|ap-northeast-3	| ami-00f09455cf36d2e08|
|ap-south-1	| ami-059a9b1093495222c|
|ap-southeast-1	| ami-01aa83ab14b00e516|
|ap-southeast-2	| ami-0d2f34c92aa48cd95|
|ca-central-1	| ami-01c592dda54e43c1a|
|eu-central-1	| ami-0245697ee3e07e755|
|eu-north-1	| ami-0813b14494048969c|
|eu-south-1	| ami-0257e70b7c6db1498|
|eu-west-1	| ami-0874dad5025ca362c|
|eu-west-2	| ami-050949f5d3aede071|
|eu-west-3	| ami-04e905a52ec8010b2|
|me-south-1	| ami-08ca9d63b8d4ec276|
|sa-east-1	| ami-02e2a5679226e293c|
|us-east-1	| ami-0adb6517915458bdb|
|us-east-2	| ami-089fe97bc00bff7cc|
|us-west-1	| ami-0528712befcd5d885|
|us-west-2	| ami-0c7ea5497c02abcaf|

## Cryptonodes

### AWS

1. Set your AWS credentials and instance configuration:
   ```bash
   export PKR_VAR_access_key=*YOUR_AWS_ACCESS_KEY*
   export PKR_VAR_secret_key=*YOUR_AWS_SECRET_KEY*
   export PKR_VAR_instance_type="c5.2xlarge"
   export PKR_VAR_source_ami="ami-0874dad5025ca362c"
   ```
2. Build the image:
    ```bash
    packer build ./cryptonode-base/aws-packer.json.pkr.hcl
    ```

After the build is finished, an image ID would be displayed, you can also view it from the AWS console at "EC2>Images>AMIs" with the filter set to "Owned by me"
