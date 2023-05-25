# shell-script2

#FOR LOOP

for variable in list
do
    # Code to be executed
done

#while loop

while condition
do
    # Code to be executed
done


#until loop

until condition
do
    # Code to be executed
done

##calculate the remaining days until the SSL certificates of a website expire:

#!/bin/bash

website="example.com"
cert_file="/path/to/certificate.pem"

expiration_date=$(openssl x509 -enddate -noout -in "$cert_file" | cut -d "=" -f 2)
expiration_epoch=$(date -d "$expiration_date" +%s)
current_epoch=$(date +%s)

remaining_days=$(( ($expiration_epoch - $current_epoch) / (60 * 60 * 24) ))

echo "Remaining days until the SSL certificate for $website expires: $remaining_days days"
