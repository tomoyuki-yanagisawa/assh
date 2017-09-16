# assh
This is a ssh command wrapper to access to AWS EC2 Instance by Tag Name

# How to install

You can install by fllowing command:

```
$ ./install.sh
```

This program copied into `/usr/local/bin`

# How to setup

This program use awscli profile named "assh". So, You should setup awscli.assh profile.

To setup awscli profile for `assh` command, type following command;

```
$ aws configure --profile assh
AWS Access Key ID [****************NNWA]:
AWS Secret Access Key [****************pJO6]:
Default region name [ap-northeast-1]:
Default output format [text]:
```

# How to use

## list your ec2 instances

```
$ assh
EC2 Instances:
incetance-web-1	ip-aa-aa-aa.ap-northeast-1.compute.internal
incetance-dev-1	ip-bb-bb-bb.ap-northeast-1.compute.internal
incetance-dev-2	ip-bb-bb-bb.ap-northeast-1.compute.internal
```

## access to ec2 instance by TagName

When if given incetance tag name is unique, you access to target instance:

```
$ assh incetance-web-1
Welcome to AmazonLinux
```

When if match several instance by given incetance tag name, you see matched instances list (and not access instance):

```
$ assh incetance-dev
incetance-dev-1	ip-bb-bb-bb.ap-northeast-1.compute.internal
incetance-dev-2	ip-bb-bb-bb.ap-northeast-1.compute.internal
```

