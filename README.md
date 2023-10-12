Creating a static webpage from AWS S3 bucket using Terraform
This project provides Terraform code to create a static webpage from an AWS S3 bucket.

Requirements
Terraform
AWS account
Usage
To use this project, follow these steps:

Clone this repository to your local machine.
Create an AWS S3 bucket to store your static webpage files.
Upload your static webpage files to the S3 bucket.
Update the variables.tf file with your S3 bucket name and the name of the static webpage file you want to serve.
Run terraform init to initialize Terraform.
Run terraform plan to generate a plan of the changes that Terraform will make.
Run terraform apply to apply the changes in the plan to your infrastructure.
Once the Terraform apply command is complete, your static webpage will be accessible at the following URL:

https://<your-s3-bucket-name>.s3.amazonaws.com/<your-static-webpage-file-name>
Example
The following example shows how to create a static webpage from an S3 bucket named my-s3-bucket and the static webpage file index.html:

variable "s3_bucket_name" {
  type = string
}

variable "static_webpage_file_name" {
  type = string
}

resource "aws_s3_bucket" "my_s3_bucket" {
  bucket = var.s3_bucket_name
  acl = "public-read"

  website {
    index_document = var.static_webpage_file_name
  }
}
To use this example, simply create a new file named variables.tf and paste the above code into it. Then, replace the var.s3_bucket_name and var.static_webpage_file_name variables with your own values.

Once you have updated the variables.tf file, you can run terraform init to initialize Terraform. Then, run terraform plan to generate a plan of the changes that Terraform will make. Finally, run terraform apply to apply the changes in the plan to your infrastructure.

Once the Terraform apply command is complete, your static webpage will be accessible at the following URL:

https://my-s3-bucket.s3.amazonaws.com/index.html
