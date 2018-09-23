# xargs Command Tips

## interpolation

If you want to know the Cidr block of some VPC in which you will use some ELB, you would get the value of the Cidr block with using this command.

```
aws --profile <profile name> elb describe-load-balancers --load-balancer-names <load balancer name> | jq '.LoadBalancerDescriptions[0].VPCId' | xargs -I{} sh -c "aws --profile <profile name> ec2 describe-vpcs --vpc-ids {} | jq '.Vpcs[0].CidrBlock'"
```

This command uses `xargs -I{} sh -c "<some commands> {}"` tips.

## Delete files whose name includes spaces

For example, you can delete 'file B' like this.
Use `-print0` option of `find` command and `-0` option of `xargs`

```
$ ls
dirA   file B fileA
$ find . -type f -print0 | xargs -0 rm
$ ls
dirA
```

## Count files in each sub directory at current directory.

This command uses `xargs -I{} sh -c "<some commands> {}"` tips.

```
$ ls -1 | xargs -I{} sh -c "echo {}; ls -1 {} | wc -l"
```