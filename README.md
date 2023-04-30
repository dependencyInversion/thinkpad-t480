# Thinkpad T480

## Enable touch gestures for Firefox



Add the following line to `/etc/security/pam_env.conf`:

```bash
MOZ_ENABLE_WAYLAND DEFAULT=0 OVERRIDE=1
```

After that log out & log in again.

---

## Undervolting

[undervolt](https://github.com/georgewhewell/undervolt/blob/master/README.rst)

`/etc/systemd/system/undervolt.service`:

```bash
# https://github.com/georgewhewell/undervolt/blob/master/README.rst
[Unit]
Description=undervolt
After=suspend.target
After=hibernate.target
After=hybrid-sleep.target

[Service]
Type=oneshot
ExecStart=/usr/local/bin/undervolt -v --core -100 --cache -100 --gpu -55 --uncore -55

[Install]
WantedBy=multi-user.target
WantedBy=suspend.target
WantedBy=hibernate.target
WantedBy=hybrid-sleep.target
```



---

## Adapting fan curve

[Thinkfan](https://thinkwiki.de/Thinkfan)

`/etc/thinkfan.conf`

```bash
(0,     0,      60)
(1,     56,     70)
(2,     65,     75)
(3,     72,     80)
(4,     75,     85)
(5,     83,     90)
(6,     86,     92)
(7,     88,     95)
(127,   93,     32767)
```

---

## Window Manager

There was some troubleshooting required installing this one.

The fix included installing `Gome Shell Integration` as well as some fiddling with Gnome's `Extension` app.

[Tiling Assistant](https://github.com/Leleat/Tiling-Assistant)