# frostproxy-package
Install frostproxy tunnel

```js
mkdir -p frostproxy/DEBIAN
```

# Build the DEB package:

```js
dpkg-deb --build frostproxy
```
```js
dpkg -i frostproxy.deb
```

# Install the package using apt-get.

```js
sudo apt-get install ./frostproxy.deb
```

# Test the frostproxy tunnel command.

```js
frostproxy tunnel localhost:3000 domain.com
```