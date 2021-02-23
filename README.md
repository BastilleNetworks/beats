This is a fork for building a hardened beats binaries

# Build

```
# ensure go is installed
$ go version

# Check out this fork
$ mkdir -p ~/go/src/github.com/elastic && cd ~/go/src/github.com/elastic
$ git clone git@github.com:BastilleNetworks/beats.git beats
# Checkout a branch to build against
$ git checkout 7.10
# Cherry-pick the patch commit from branch 7.11 - skip this step on 7.11
$ git cherry-pick f7dc0759ed588b4742278d39b06115ee99109ce2
# Enter the beat you want to build
$ cd filebeat
$ VERSION_QUALIFIER='hardened' PLATFORMS='linux/amd64' mage package
...
# The deb package can be found under ./distribution
```
