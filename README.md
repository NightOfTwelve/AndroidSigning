# Android Signing Automatic Config

Config keyStore and key in a xml and sign your apk easily.

## Usage

Default config file is `~/.android_key_store.xml`, sample config as:

``` xml
<keystores>
    <keystore>
        <store-name>keystore1</store-name>
        <store-path>~/keys/keystore1.key</store-path>
        <store-password>password</store-password>
        <aliases>
            <alias>
                <alias-name>alias1</alias-name>
                <alias-password>password</alias-password>
            </alias>
        </aliases>
    </keystore>

    <keystore>
        <store-name>keystore2</store-name>
        <store-path>~/keys/keystore2.key</store-path>
        <store-password>password</store-password>
        <aliases>
            <alias>
                <alias-name>alias1</alias-name>
                <alias-password>password</alias-password>
            </alias>
            <alias>
                <alias-name>alias2</alias-name>
                <alias-password>password</alias-password>
            </alias>
        </aliases>
    </keystore>
</keystores>

```

In top level `build.gradle` add this to classpath
``` groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:1.0.0'
        classpath 'org.quanqi:android-signing:0.1.0'

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}
```

apply plugin in application module

```
apply plugin: 'org.quanqi.android-signing'
```

Now in your signingConfigs these signingConfig were available:
* keystore1_alias1
* keystore2_alias1
* keystore2_alias2

Enjoy.

## LICENSE

APACHE-2