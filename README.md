# alpine-alt-nodejs

This is an alternative repository for the latest nodejs packages using alpine v3.2

+ **nodejs**: 4.2.0-r0
+ **libuv**: 1.7.5-r0

## FAQ

**How do I use it?**

    echo 'http://ghostbar.github.io/alpine-alt-nodejs/v3.2/pkgs/v3.2' >> /etc/apk/repositories
    apk --update add nodejs

You could download the package directly as well with:

    curl -O https://ghostbar.github.io/alpine-alt-nodejs/v3.2/pkgs/v3.2/x86_64/nodejs-4.2.0-r0.apk
    apk add --allow-untrusted nodejs-4.2.0-r0.apk

**I'm getting a BAD signature**

You probably changed the name of the package, since the signature is linked to the package name.


**Is this really necessary? I could just install the latest nodejs from edge, don't I?**

Yes, you can install it but it won't work. v3.2 and edge are using different gcc (4.9 on v3.2 and 5.2 on edge) and there was a change of ABI which renders the package unusable if linked with an older gcc installation. So when you try to install a package with npm it will give you issues with symbols not found.
