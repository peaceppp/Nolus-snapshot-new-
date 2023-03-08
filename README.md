Stop service nolus

```
sudo systemctl stop nolusd
```

reset chain data

```
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
```
```
rm -rf $HOME/.nolus/data
```

Download Snapshot 

```
curl -L https://snapshoots.nolus.kaelvnode.xyz/nolus/nolus-snapshot-20230302.tar.lz4 | tar -Ilz4 -xf - -C 
```

```
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

Restart service nolus

```
sudo systemctl restart nolusd
```

Check Logs nolus

```
sudo journalctl -u nolusd -f --no-hostname -o cat
```
