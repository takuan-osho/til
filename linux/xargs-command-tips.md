# xargs Command Tips

## interpolation

If you want to know the Cidr block of some VPC in which you will use some ELB, you would get the value of the Cidr block with using this command.

```
aws --profile <profile name> elb describe-load-balancers --load-balancer-names <load balancer name> | jq '.LoadBalancerDescriptions[0].VPCId' | xargs -I{} sh -c "aws --profile <profile name> ec2 describe-vpcs --vpc-ids {} | jq '.Vpcs[0].CidrBlock'"
```

This command uses `xargs -I{} sh -c "<some commands> {}"` tips.