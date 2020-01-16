# Amazon AWS


## AWS CLI

### Install

https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html

```
$ pip3 install awscli --upgrade --user
```

Update PATH (.bash_profile)
```
export PATH=$PATH:~/Library/Python/3.7/bin
```

### Configure

https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html

```
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

```
$ aws s3 ls
```

```
$ aws configure --profile produser
AWS Access Key ID [None]: AKIAI44QH8DHBEXAMPLE
AWS Secret Access Key [None]: je7MtGbClwBF/2Zp9Utk/h3yCo8nvbEXAMPLEKEY
Default region name [None]: us-east-1
Default output format [None]: text
```

```
$ aws s3 ls --profile produser
```

## AWS SAM CLI

### Install

```
brew tap aws/tap
brew install aws-sam-cli
```

```
sam --version
```

### Build & Deploy

```
#Step 1 - Download a sample application
sam init

#Step 2 - Build your application
cd sam-app
sam build

#Step 3 - Deploy your application
sam deploy --guided
```
