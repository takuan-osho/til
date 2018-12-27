jq Command Tips

## Alternative operator

refs. https://stedolan.github.io/jq/manual/#Alternativeoperator://

Use it like this. This command below will show some statuses of RDS for PostgreSQL.

```console
$ cat region-rds.txt
us-east-2
us-east-1
us-west-1
us-west-2
ap-south-1
ap-northeast-2
ap-southeast-1
ap-southeast-2
ap-northeast-1
ca-central-1
eu-central-1
eu-west-1
eu-west-2
eu-west-3
eu-north-1
sa-east-1

$ profile=sample
$ cat region-rds.txt | xargs -I{} sh -c "echo [{}]; aws --profile $profile --region {} rds describe-db-instances | jq '.DBInstances[] | select(.Engine == \"postgres\")' | jq -r '.DBInstanceIdentifier,.DBInstanceArn,.EngineVersion,.AutoMinorVersionUpgrade,.Null // \" \"'; echo"
```