## Sidekiq

```
bundle exec sidekiq
bundle exec sidekiq -d -L log/sidekiq.log
ps aux | grep sidekiq
```

## Redis
```
redis-server

example redis set value on mobile number

$redis = Redis.new(url: 'redis://localhost:6379/0')

$redis.set("#{@otp_value}:#{@mobile_number}", @otp_value)
$redis.expire("#{@otp_value}:#{@mobile_number}", 300) 

If $redis.keys("*:#{@mobile_number}").present?
     @otp_value = $redis.keys("*:#{@mobile_number}").map { |key| $redis.get(key) }[0]
End
$redis.del("#{params[:otp]}:#{params[:mobile_number]}")
```

## Redis Specific version Update

```
sudo apt-get remove --purge -y redis-server
sudo apt-get update
sudo apt-get install -y build-essential tcl
wget http://download.redis.io/releases/redis-6.2.0.tar.gz && tar xzf redis-6.2.0.tar.gz && cd redis-6.2.0 && make
sudo make install
sudo mkdir -p /etc/redis
sudo cp redis.conf /etc/redis
sudo systemctl restart redis
```

### Find Ip Address System

```
 Curl ifconfig.me
```

## Rails Log Check On Server:

```
tail -f log/development.log | grep error

```

## Gem Library Version Show  
```
bundle info package_name
```


## Get my ssh key
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
ssh-add ~/.ssh/id_rsa
eval "$(ssh-agent -s)"
cat ~/.ssh/id_rsa.pub

Add on GitHub: git ssh && gpg and repo clone via ssh  git clone git@github.com:user/repo.git 

on server create ./ssh/authorized_keys file and put ssh and access server on terminal

sudo vim ~/.ssh/authorized_keys

excess on terminal

ssh ubuntu@3.111.198.217(public ip)
```

## Database Dump On Server
```
pg_dump -U user_name -h localhost database_name >> file_name.sql

Command to download sever file to local system

add ssh key on authorized_keys to attached scp on terminal

scp ubuntu@13.233.174.226:/home/ubuntu/backend/file_name.sql /Users/glosys/Desktop(local system path)

import all data in our database via command line

Check system user name: whoami

psql -h localhost -d database_name -U  system_user_name -f /Users/system_user_name/Desktop/file_name.sql
```

## Running Port On Our System

```
lsof -i -P -n | grep LISTEN
lsof -i :3000
Kill -9 ip
```


## Screen Session Setup

```
brew install screen

screen -r session_name;  #att session
screen -S session_name;  new session create
screen -X -S sidekiq_running quit;

```


## Postgresql

```
brew install postgresql@15
brew services start postgresql@15
psql --version
psql -U your_username -d your_database;
SELECT * FROM pg_stat_activity;
SELECT pg_terminate_backend(your_pid); kill activitys
```
