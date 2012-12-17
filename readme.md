#DumpPublicKey for omaha

#How to use

###1. Generate public key

    >cd src
    >java java com/android/dumpkey/DumpPublicKey C:\keys\cup.pub.der

###2. Paste public key(output of 1.) to \omaha\net\cup_pubkey.3.h

###3. Modify omaha code

\omaha\base\security\rsa.cc

    //#define MOD(i) (mod[2 + 2*(i)] + mod[1 + 2*(i)])  // +mod[1+2*(i)] to deobscure
    #define MOD(i) mod[2 + 2*(i)]


#Reference

- [http://code.google.com/p/omaha/](http://code.google.com/p/omaha/)
- [original source](http://omapzoom.org/?p=platform/system/core.git;a=tree;f=libmincrypt;h=67e5c6a2617eb7aca5d88165c809297bf7dc2e91;hb=HEAD)
