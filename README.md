# cognito-backup 👫→💾
Amazon doesn't have any way of backing up their AWS Cognito User Pools.
So in my frustrating times working with AWS Cognito, I wrote this tool. `cognito-backup` is a simple CLI for backing up the user data, and can also restore afterwards. <b>Note: AWS has no way of extracting the passwords of your users so you need to store these separately 😵</b>



## Requirements

Requires node 8 or newer

## Install
```
npm install -g cognito-backup
```

## Usage
Backup all users in a single user pool:  
`cognito-backup backup-users <user-pool-id> <options>`

Backup all users in all user pools for this account:  
`cognito-backup backup-all-users <options>`

Restore users to a single user pool:   
`cognito-backup restore-users <user-pool-id> <temp-password>`

Run `cognito-backup` for complete usage.

## Examples

`cognito-backup backup-users eu-west-1_1_12345`  
`cognito-backup backup-users eu-west-1_1_12345 --region eu-west-1 --file mypool.json`  
`cognito-backup backup-all-users eu-west-1_1_12345 --region eu-west-1 --dir output`  
`cognito-backup restore-users eu-west-1_12345 Abcd.1234 --file eu-west-1_12345.json`

## Related

- https://github.com/mifi/dynamodump
