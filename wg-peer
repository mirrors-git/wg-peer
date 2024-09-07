#!/bin/bash

readonly INTERFACE="wg0"

# Generate peer keys
readonly PRIVATE_KEY=$(wg genkey)
readonly PUBLIC_KEY=$(echo ${PRIVATE_KEY} | wg pubkey)
readonly PRESHARED_KEY=$(wg genpsk)

# Read server key from interface
readonly SERVER_PUBLIC_KEY=$(wg show ${INTERFACE} public-key)

# Get next free peer IP (This will break after x.x.x.255)
readonly PEER_ADDRESS=$(wg show ${INTERFACE} allowed-ips | cut -f 2 | awk -F'[./]' '{print $1"."$2"."$3"."1+$4"/"$5}' | sort -t '.' -k 1,1 -k 2,2 -k 3,3 -k 4,4 -n | tail -n1)

# Add peer
wg set ${INTERFACE} peer ${PUBLIC_KEY} preshared-key <(echo ${PRESHARED_KEY}) allowed-ips ${PEER_ADDRESS}

# Logging
echo "Added peer ${PEER_ADDRESS} with public key ${PUBLIC_KEY}"

# Generate peer config QR code
cat << END_OF_CONFIG | qrencode -t ANSIUTF8
[Interface]
Address = ${PEER_ADDRESS}
PrivateKey = ${PRIVATE_KEY}
DNS = 8.8.8.8 (Your internal DNS server here)

[Peer]
PublicKey = ${SERVER_PUBLIC_KEY}
PresharedKey = ${PRESHARED_KEY}
AllowedIPs = 0.0.0.0/0
Endpoint = example.com:443 (Your external Wireguard endpoint here)
END_OF_CONFIG
