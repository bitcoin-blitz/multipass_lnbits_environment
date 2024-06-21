# multipass_lnbits_environment

Aufsetzen einer lokalen lnbits testumgebung unter macOS mit Hilfe von mulitpass 

https://lnbits.com/
https://docs.lnbits.org/

https://multipass.run/
https://multipass.run/docs

```
multipass launch docker --name lnbits-docker --network en0
mulipass shell lnbits-docker
docker pull lnbits/lnbits
wget https://raw.githubusercontent.com/lnbits/lnbits/main/.env.example -O .env
mkdir data
docker run --detach --publish 5000:5000 --name lnbits --volume ${PWD}/.env:/app/.env --volume ${PWD}/data/:/app/data lnbits/lnbits
```
