# Routinator-RPKI-Relying

# Installation
Ubuntu 24.04.3 LTS

## Install Dependencies
sudo apt install \
  ca-certificates \
  curl \
  gnupg \
  lsb-release

## Add GPG key from NLnet Labs
curl -fsSL https://packages.nlnetlabs.nl/aptkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/nlnetlabs-archive-keyring.gpg

## Add repostiory and update
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/nlnetlabs-archive-keyring.gpg] https://packages.nlnetlabs.nl/linux/ubuntu \
$(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/nlnetlabs.list > /dev/null

## Install Routinator
sudo apt install routinator

## Show status routinator
sudo systemctl status routinator

## Configure routinator 
/etc/routinator/routinator.conf

## Restart Routinator
sudo systemctl restart routinator

## Check service with HTTP json
curl http://192.168.100.137:8323/json\?select-asn\=24211

Result
{
  "metadata": {
    "generated": 1758034201,
    "generatedTime": "2025-09-16T14:50:01Z"
  }
,
  "roas": [
    { "asn": "AS24211", "prefix": "103.49.220.0/23", "maxLength": 23, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "103.49.222.0/23", "maxLength": 23, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "103.49.220.0/22", "maxLength": 22, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.240.0/24", "maxLength": 24, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.240.0/23", "maxLength": 23, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.242.0/23", "maxLength": 23, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.244.0/23", "maxLength": 23, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.246.0/24", "maxLength": 24, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.247.0/24", "maxLength": 24, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.246.0/23", "maxLength": 23, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "203.190.240.0/21", "maxLength": 21, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000::/48", "maxLength": 48, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000::/34", "maxLength": 34, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000:4000::/34", "maxLength": 34, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000:8000::/34", "maxLength": 34, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000:fffe::/48", "maxLength": 48, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000:c000::/34", "maxLength": 34, "ta": "apnic" },
    { "asn": "AS24211", "prefix": "2402:a000::/32", "maxLength": 32, "ta": "apnic" }
  ]

## You can check via web ui to via 
http://192.168.100.137:8323/ui
