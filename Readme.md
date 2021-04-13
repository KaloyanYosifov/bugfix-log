# Laravel bugs

- Major bug I always forget - ***14.09.2020***. When you pass the whole model in associate, after we call model's method `toJson` it ends in an endless loop where we exhaus all our bytes.

# Amazon deployment

- Create a snapshot of the current database RDS
- Create an elastic beanstalk environment with the same settings as the old instance, but use the Application Load Balancer
- If using external Redis add to the inbound rules the new elastic beanstalk security group for ec2 instance
- Use `eb printenv` and `eb setenv` to update the EB environments instead of doing it manually. 
- When using `eb setenv` even when escaping the space, for some reason environment values with spaces(even surrounded with double quotes) results in an error add the ones with spaces manually.
- If using Amazon Linux 2 with PHP, the environment variables are automatically pushed to the php request. So only the apache or nginx server has the environments. 
- If we want to have the environments set for `web-app` we need to do this - [Link](https://aws.amazon.com/premiumsupport/knowledge-center/elastic-beanstalk-env-variables-linux2/)
- Amazon linux 2 uses `composer.phar` instead of `composer` name :facepalm.

# Docker issues

## Mysql -- lower_case_table_name has different case sensitivity than original

- ***07.04.2021***: Delete the mysql data volume from docker and the computer and rebuild mysql docker container (you can export the database and import it later instead of deleting it with the docker volum).

# React Native Issues

## Unable to upload file 

- If you are using [React Native Debugger](https://github.com/jhen0409/react-native-debugger) and you have enabled network logs you must disabled the "Network" logging feature, because the library owner changes "FormData", "Blob" and "File" and makes uploading files impossible. 

# Valet share issue

## Bad Gateway 

- Run `valet start` to start valet.
