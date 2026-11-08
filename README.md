### python script and a service (call it a subsctiption cli) for an xray-core
> [!CAUTION]
> # **THIS IS EXTREMLY VIBE CODED, USE AT YOUR RISK, I DO NOT KNOW WHAT THE FUCK DID CLAUDE WROTE HERE, IT WORKS FOR ME, IT MIGHT BE NOT FOR YOU**
1. install xray-core. if you're on arch **btw**, you can install it from aur
2. do these `sudo install -m755 xray-sub /usr/local/bin/xray-sub` `sudo install -m644 xray-tun.service /etc/systemd/system/` **THIS MIGHT BE DIFFERENT ON YOUR SYSTEM SO BE CAREFUL**
3. create a xray directory with right rights `sudo install -d -m700 /etc/xray`
4. create a `subscription.url` file inside `/etc/xray/`
5. `sudo xray-sub list` then `sudo xray-sub use N` or if you want ipv6 `sudo xray-sub --ipv6 use N`
6. `sudo systemctl enable --now xray-tun` for it to be enabled on startup and started (if you just want to start it without autostart on startup `sudo systemctl start xray-tun`)

it will also remove `inbounds` that are present in the configs, only keeping `inbounds` that are needed for the tunnel to work
it also caches the subsctiption for an offline use!
