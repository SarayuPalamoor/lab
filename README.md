Access Policy that needs to be configured on SNS:
{
  "Version": "2012-10-17",
  "Id": "__default_policy_ID",
  "Statement": [
    {
      "Sid": "__default_statement_ID",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::404147232814:root"
      },
      "Action": [
        "SNS:GetTopicAttributes",
        "SNS:SetTopicAttributes",
        "SNS:AddPermission",
        "SNS:RemovePermission",
        "SNS:DeleteTopic",
        "SNS:Subscribe",
        "SNS:ListSubscriptionsByTopic",
        "SNS:Publish"
      ],
      "Resource": "arn:aws:sns:ap-southeast-2:404147232814:top",
      "Condition": {
        "StringEquals": {
          "AWS:SourceAccount": "404147232814"
        }
      }
    },
    {
      "Sid": "AllowS3Publish",
      "Effect": "Allow",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Action": "SNS:Publish",
      "Resource": "arn:aws:sns:ap-southeast-2:404147232814:top",
      "Condition": {
        "StringEquals": {
          "AWS:SourceAccount": "404147232814"
        }
      }
    }
  ]
}
