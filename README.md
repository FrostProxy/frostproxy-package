frostproxy-package
Install the FrostProxy CLI to manage tunnels via the hosted API.

Build the DEB package
```bash
dpkg-deb --build frostproxy-package
```

Install the package
```bash
sudo apt-get install ./frostproxy-package.deb
```

Reinstall after changes
```bash
sudo apt-get remove frostproxy
dpkg-deb --build frostproxy-package
sudo apt-get install ./frostproxy-package.deb
```

CLI usage
```bash
frostproxy help
frostproxy config token <ID>
frostproxy tunnel <target> <domain> [--ssl|--no-ssl] [--debug]
frostproxy delete <domain> [--debug]
frostproxy list tunnels [--debug]
```

Behavior
- Stores token at `/var/frostproxy/config.cfg` via `frostproxy config token <ID>`.
- Base URL defaults to `https://frostproxy.com`; override with `FROSTPROXY_BASE`.
- Debug/dry-run: set `FROSTPROXY_DEBUG=true` or pass `--debug` to print the request without calling the API (still validates arguments/config).

Notes
- `postinst` ensures `/var/frostproxy` exists and the CLI is executable.
- Remove: `apt remove frostproxy`.
