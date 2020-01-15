# Amazon AWS


## AWS CLI

### Installation

https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html

```
$ pip3 install awscli --upgrade --user
```

Update PATH (.bash_profile)
```
export PATH=$PATH:~/Library/Python/3.7/bin
```

### Configuration

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
