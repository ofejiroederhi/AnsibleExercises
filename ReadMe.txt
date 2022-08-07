

# Run this in your exercise directory
touch inventory
echo [all] > inventory

#Add Public IP to Inventory
aws ec2 describe-instances \
\
        --query 'Reservations[*].Instances[*].PublicIpAddress' \
      --filters "Name=tag:Project,Values=udacity" \
      --output text >> inventory