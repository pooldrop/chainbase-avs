## System Requirements
```bash
sudo apt update && sudo apt upgrade -y
```
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
docker version
```
```bash
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)

curl -L "https://github.com/docker/compose/releases/download/"$VER"/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose
docker-compose --version
```
## Install Eigenlayer CLI
```bash
curl -sSfL https://raw.githubusercontent.com/layr-labs/eigenlayer-cli/master/scripts/install.sh | sh -s

export PATH=$PATH:~/bin

eigenlayer --version
```
```bash
git clone https://github.com/chainbase-labs/chainbase-avs-contracts.git
cd chainbase-avs-contracts
```
اینجا ابتدا یک ولت EVM بسازید و از وبسایت زیر برای آن یک عدد توکن تستی اتریوم بر روی شبکه holesky بگیرید 



https://cloud.google.com/application/web3/faucet/ethereum/holesky

در کامن پایین لازم است به جای <your-private-key> باید private key همین ولت EVM خود را قرار دهید
```bash
eigenlayer operator keys import --key-type ecdsa chainbase <your-private-key>
```
```bash
cp /root/.eigenlayer/operator_keys/chainbase.ecdsa.key.json .
```
```bash
eigenlayer operator config create
```
اینجا ابتدا y سپس اینتر بزنید 

در قسمت بعدی آدرس ولت EVM که توکن تستی دریافت کردید وارد کنید

اینجا فقط اینتر بزنید 

اینجا باید یک RPC از شبکه holesky بدید که می توانید از RPC پایین استفاده کنید

اینجا holesky را انتخاب کنید 

اینجا local_keystore را انتخاب کنید

اینجا متن زیر را قرار دهید
```
/root/.eigenlayer/operator_keys/chainbase.ecdsa.key.json
```

حالا وارد گیت هاب خود بشید و یک repository بسازید

حالا وارد وبسایت زیر شوید و یک لوگو برای خود با فرمت png دانلود کنید

https://www.vecteezy.com/free-png/skull

سپس وارد وبسایت زیر شوید و حجم لوگو دانلود شده را کاهش دهید

https://imagecompressor.11zon.com/en/compress-png/compress-png-to-900kb

حالا لوگو را داخل گیت هاب آپلود کنید سپس یک فایل به نام metadata.json بسازید و داخل آن اطلاعات زیر را قرار دهید
```
{
  "name": "<your-name>",
  "website": "<your-website>",
  "description": "<anything>",
  "logo": "https://raw.githubusercontent.com/",
  "twitter": "<your-twitter>"
}
```




