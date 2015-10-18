# alpine-alt-nodejs

This is an alternative repository for the latest nodejs packages using alpine v3.2

+ **nodejs**: 4.2.1-r0
+ **libuv**: 1.7.5-r0

## FAQ

**How do I use it?**

    echo 'http://ghostbar.github.io/alpine-alt-nodejs/v3.2/pkgs/v3.2' >> /etc/apk/repositories
    apk --update --allow-untrusted add nodejs

You could download the package directly as well with:

    curl -O https://ghostbar.github.io/alpine-alt-nodejs/v3.2/pkgs/v3.2/x86_64/nodejs-4.2.1-r0.apk
    apk add --allow-untrusted nodejs-4.2.1-r0.apk

**Which way is better to download?**

If you use it in the repo-way then you will always download and install the latest nodejs. If you decide to download it with curl then you will just use that version. This is not bad, necessarily, the version will keep existing here, it won't be deleted if there's a new version packaged, but yet, is an older version.

**But I'm a crazy person that wants it's docker image as small as possible, downloading the APKINDEX.tar.gz will bloat it!**

If that's what worries you, then just do a `rm -rf /var/cache/apk/*` and you're done.

**I'm getting a BAD signature**

You probably changed the name of the package, since the signature is linked to the package name.

**I'm getting an UNTRUSTED signature**

You need to use `--allow-untrusted` when launching `apk` commands, including `apk update`.


**Is this really necessary? I could just install the latest nodejs from edge, don't I?**

Yes, you can install it but it won't work. v3.2 and edge are using different gcc (4.9 on v3.2 and 5.2 on edge) and there was a change of ABI which renders the package unusable if linked with an older gcc installation. So when you try to install a package with npm it will give you issues with symbols not found.
