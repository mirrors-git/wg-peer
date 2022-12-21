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

### Examples
- list peers: `wg-peer l`
- add a new peer: `wg-peer a`
- show client configuration for peer: `wg-peer s kTU5yhp1qPBHsKhKs4aSgPKRotU4bGPhl3y8dHD1Ki4=`
- delete peer: `wg-peer d kTU5yhp1qPBHsKhKs4aSgPKRotU4bGPhl3y8dHD1Ki4=`

### Screenshots
![Screenshot](https://images2.imgbox.com/0c/a5/i8xYgyra_o.png)
