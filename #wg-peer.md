# Manage Wireguard peers (IPv4 only)

List, add or delete Wireguard peers. Also show client configuration for added peers.

```
wg-peer [add|show <peer>|del <peer>|list]
```

where:
- **a[dd]**  : add a new peer
- **s[how]** : show peer configuration
- **d[el]**  : delete peer
- **l[ist]** : list peers
**<peer>*** is the peer public key as shown by list command

### Examples
- list peers: `wg-peer l`
- add a new peer: `wg-peer a`
- show client configuration for peer: `wg-peer s kTU5yhp1qPBHsKhKs4aSgPKRotU4bGPhl3y8dHD1Ki4=`
- delete peer: `wg-peer d kTU5yhp1qPBHsKhKs4aSgPKRotU4bGPhl3y8dHD1Ki4=`

### Screenshots
![Screenshot](https://images2.imgbox.com/52/1a/1bnOBlaj_o.png)
![Screenshot](https://images2.imgbox.com/0f/0a/DbVVJ3sY_o.jpg)
![Screenshot](https://images2.imgbox.com/87/04/eM1axzxl_o.png)
![Screenshot](https://images2.imgbox.com/ec/68/56dASc2J_o.png)