Description: Makefile customizations for Debian package
 Activate PRNG X9.17 with SHA-1
 activate libraries needed for build on Linux
 set correct install paths
 add dpkg-buildflags for hardening
Origin: vendor
Forwarded: not-needed
--- a/Makefile
+++ b/Makefile
@@ -6,7 +6,7 @@ CC = gcc
 ##################################################################
 # Compilation flags
 # You should comment the line below for AIX+native cc
-FLAGS = -Wall
+FLAGS = -Wall `dpkg-buildflags --get CFLAGS` `dpkg-buildflags --get LDFLAGS`
 
 ##################################################################
 # Libraries
@@ -34,16 +34,16 @@ CRYPTED_PASS = APG_USE_CRYPT
 # DO NOT EDIT THE LINE BELOW !!!
 USE_SHA = APG_USE_SHA
 # Coment this if you want to use PRNG X9.17 with SHA-1
-USE_SHA = APG_DONOTUSE_SHA
+# USE_SHA = APG_DONOTUSE_SHA
 
 ##################################################################
 # Directories
 # Install dirs
 INSTALL_PREFIX = /usr/local
 APG_BIN_DIR = /bin
-APG_MAN_DIR = /man/man1
+APG_MAN_DIR = /share/man/man1
 APGD_BIN_DIR = /sbin
-APGD_MAN_DIR = /man/man8
+APGD_MAN_DIR = /share/man/man8
 
 ####################################################################
 # If you plan to install APG daemon you should look at lines below #
@@ -59,7 +59,7 @@ APGD_MAN_DIR = /man/man8
 # Linux
 #
 # Uncoment line below for LINUX
-#CS_LIBS = -lnsl
+CS_LIBS = -lnsl
 
 ####################################################################
 # Solaris
@@ -75,7 +75,7 @@ APGD_MAN_DIR = /man/man8
 
 # ====== YOU DO NOT NEED TO MODIFY ANYTHING BELOW THIS LINE ======
 # Find group ID for user root
-FIND_GROUP = `grep '^root:' /etc/passwd | awk -F: '{ print $$4 }'`
+FIND_GROUP = `getent passwd root | awk -F: '{ print $$4 }'`
 
 PROGNAME = apg
 CS_PROGNAME = apgd
