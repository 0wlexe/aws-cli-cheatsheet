## CloudWatch
List information about an alarm
```shell
aws cloudwatch describe-alarms | jq -r ‘.MetricAlarms[ ] | .AlarmName+” “+.Namespace+” “+.StateValue’
```

Delete an alarm or alarms (you can delete up to 100 at a time)
```shell
aws cloudwatch delete-alarms --alarm-names (alarmnames)
```
