# mawstool

This is just a wrapper script around awscli. It makes my life personally easier when doing manual testing.

## Setup
The flags you can use (shown in `mawstool --help`) will default to certain values or pull from your environment

The environment variable it looks for is the flag in all capital letters. For example, the environment variable that will set `--aws_key` is `AWS_KEY`, but supplying the flag will always override the environment variable.

This type of setup is helpful for me when I do rapid testing, I usually stay in one region so I can set these variables and run smaller commands.

## Example for hibernation testing
```
mawstool create_hibernation_instance \
         -n mitchdz-arm64-hibernation \
         --aws_ami ami-0ac08e87e03533a1d \
         --aws_instance_type t3.micro \
         --aws_security_group sg-0e03e00997fa53926
mawstool hibernate_then_start -n mitchdz-arm64-hibernation
```
