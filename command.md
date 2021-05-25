```shell script
dh_make --help
usage: dh_make [-h] [-a] [-c <type>] [--copyrightfile <file>] [-d] [--docs] [-e <address>] [-f <file>] [-n] [-o <dir>] [-p <name>] [-t <dir>] [-y]
               [--createorig] [--with-emacs] [-C <cls> | -s | -i | -l | --python] [-v]

prepare Debian packaging from an original source archive

optional arguments:
  -h, --help            show this help message and exit
  -a, --addmissing      reprocess package and add missing files
  -c <type>, --copyright <type>
                        use <type> of license in copyright file (apache|artistic|bsd|gpl|gpl2|gpl3|isc|lgpl|lgpl2|lgpl3|mit|custom)
  --copyrightfile <file>
                        Template to use for custom copyright
  -d, --defaultless     skip the default Debian and package class templates
  --docs                create a separate docs package
  -e <address>, --email <address>
                        use <address> as the maintainer e-mail address
  -f <file>, --file <file>
                        use <file> as the original source archive
  -n, --native          the program is Debian native, don't generate .orig
  -o <dir>, --overlay <dir>
                        reprocess package using templates in <dir>
  -p <name>, --packagename <name>
                        force package name to be <name>
  -t <dir>, --templates <dir>
                        apply customizing templates from <dir>
  -y, --yes             automatic yes to prompts and run non-interactively
  --createorig          create orig.tar.xz file
  --with-emacs          add files for emacsen
  -C <cls>, --packageclass <cls>
                        set package class (s|i|l|p)
  -s, --single          set package class to single
  -i, --indep           set package class to arch-independent
  -l, --library         set package class to library
  --python              set package class to python
  -v, --version         show program's version number and exit







dpkg-buildpackage --help
Usage: dpkg-buildpackage [<option>...]

Options:
      --build=<type>[,...]    specify the build <type>: full, source, binary,
                                any, all (default is 'full').
  -F, --build=full            normal full build (source and binary; default).
  -g, --build=source,all      source and arch-indep build.
  -G, --build=source,any      source and arch-specific build.
  -b, --build=binary          binary-only, no source files.
  -B, --build=any             binary-only, only arch-specific files.
  -A, --build=all             binary-only, only arch-indep files.
  -S, --build=source          source-only, no binary files.
  -nc, --no-pre-clean         do not pre clean source tree (implies -b).
      --pre-clean             pre clean source tree (default).
      --no-post-clean         do not post clean source tree (default).
  -tc, --post-clean           post clean source tree.
  -D, --check-builddeps       check build dependencies and conflicts (default).
  -d, --no-check-builddeps    do not check build dependencies and conflicts.
      --ignore-builtin-builddeps
                              do not check builtin build dependencies.
  -P, --build-profiles=<profiles>
                              assume comma-separated build <profiles> as active.
      --rules-requires-root   assume legacy Rules-Requires-Root field value.
  -R, --rules-file=<rules>    rules file to execute (default is debian/rules).
  -T, --rules-target=<target> call debian/rules <target>.
      --as-root               ensure -T calls the target with root rights.
  -j, --jobs[=<number>|auto]  jobs to run simultaneously (passed to <rules>),
                                forced mode.
  -J, --jobs-try[=<number>|auto]
                              jobs to run simultaneously (passed to <rules>),
                                opt-in mode (default is auto).
  -r, --root-command=<command>
                              command to gain root rights (default is fakeroot).
      --check-command=<command>
                              command to check the .changes file (no default).
      --check-option=<opt>    pass <opt> to check <command>.
      --hook-<name>=<command> set <command> as the hook <name>, known hooks:
                                init preclean source build binary buildinfo
                                changes postclean check sign done
      --buildinfo-option=<opt>
                              pass option <opt> to dpkg-genbuildinfo.
  -p, --sign-command=<command>
                              command to sign .dsc and/or .changes files
                                (default is gpg2 or gpg).
  -k, --sign-key=<keyid>      the key to use for signing.
  -ap, --sign-pause           add pause before starting signature process.
  -us, --unsigned-source      unsigned source package.
  -ui, --unsigned-buildinfo   unsigned .buildinfo file.
  -uc, --unsigned-changes     unsigned .buildinfo and .changes file.
      --no-sign               do not sign any file.
      --force-sign            force signing the resulting files.
      --admindir=<directory>  change the administrative directory.
  -?, --help                  show this help message.
      --version               show the version.

Options passed to dpkg-architecture:
  -a, --host-arch <arch>      set the host Debian architecture.
  -t, --host-type <type>      set the host GNU system type.
      --target-arch <arch>    set the target Debian architecture.
      --target-type <type>    set the target GNU system type.

Options passed to dpkg-genchanges:
  -si                         source includes orig, if new upstream (default).
  -sa                         source includes orig, always.
  -sd                         source is diff and .dsc only.
  -v<version>                 changes since version <version>.
  -m, --release-by=<maint>    maintainer for this release is <maint>.
  -e, --build-by=<maint>      maintainer for this build is <maint>.
  -C<descfile>                changes are described in <descfile>.
      --changes-option=<opt>  pass option <opt> to dpkg-genchanges.

Options passed to dpkg-source:
  -sn                         force Debian native source format.
  -s[sAkurKUR]                see dpkg-source for explanation.
  -z, --compression-level=<level>
                              compression level to use for source.
  -Z, --compression=<compressor>
                              compression to use for source (gz|xz|bzip2|lzma).
  -i, --diff-ignore[=<regex>] ignore diffs of files matching <regex>.
  -I, --tar-ignore[=<pattern>]
                              filter out files when building tarballs.
      --source-option=<opt>   pass option <opt> to dpkg-source.




debsign --help
Usage: debsign [options] [changes, buildinfo, dsc or commands file]
  Options:
    -r [username@]remotehost
                    The machine on which the files live. If given, then a
                    changes file with full pathname (or relative to the
                    remote home directory) must be given as the main
                    argument in the rest of the command line.
    -k<keyid>       The key to use for signing
    -p<sign-command>  The command to use for signing
    -e<maintainer>  Sign using key of <maintainer> (takes precedence over -m)
    -m<maintainer>  The same as -e
    -S              Use changes file made for source-only upload
    -a<arch>        Use changes file made for Debian target architecture <arch>
    -t<target>      Use changes file made for GNU target architecture <target>
    --multi         Use most recent multiarch .changes file found
    --re-sign       Re-sign if the file is already signed.
    --no-re-sign    Don't re-sign if the file is already signed.
    --debs-dir <directory>
                    The location of the files to be signed when called from
                    within a source tree (default ..)
    --no-conf, --noconf
                    Don't read devscripts config files;
                    must be the first option given
    --help          Show this message
    --version       Show version and copyright information
  If an explicit filename is specified, it along with any child .buildinfo and
  .dsc files are signed. Otherwise, debian/changelog is parsed to find the
  changes file.

Default settings modified by devscripts configuration files:
  (none)



gpg --help
gpg (GnuPG) 2.2.19
libgcrypt 1.8.5
Copyright (C) 2019 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Home: /home/fastcfs/.gnupg
Supported algorithms:
Pubkey: RSA, ELG, DSA, ECDH, ECDSA, EDDSA
Cipher: IDEA, 3DES, CAST5, BLOWFISH, AES, AES192, AES256, TWOFISH,
        CAMELLIA128, CAMELLIA192, CAMELLIA256
Hash: SHA1, RIPEMD160, SHA256, SHA384, SHA512, SHA224
Compression: Uncompressed, ZIP, ZLIB, BZIP2

Syntax: gpg [options] [files]
Sign, check, encrypt or decrypt
Default operation depends on the input data

Commands:

 -s, --sign                  make a signature
     --clear-sign            make a clear text signature
 -b, --detach-sign           make a detached signature
 -e, --encrypt               encrypt data
 -c, --symmetric             encryption only with symmetric cipher
 -d, --decrypt               decrypt data (default)
     --verify                verify a signature
 -k, --list-keys             list keys
     --list-signatures       list keys and signatures
     --check-signatures      list and check key signatures
     --fingerprint           list keys and fingerprints
 -K, --list-secret-keys      list secret keys
     --generate-key          generate a new key pair
     --quick-generate-key    quickly generate a new key pair
     --quick-add-uid         quickly add a new user-id
     --quick-revoke-uid      quickly revoke a user-id
     --quick-set-expire      quickly set a new expiration date
     --full-generate-key     full featured key pair generation
     --generate-revocation   generate a revocation certificate
     --delete-keys           remove keys from the public keyring
     --delete-secret-keys    remove keys from the secret keyring
     --quick-sign-key        quickly sign a key
     --quick-lsign-key       quickly sign a key locally
     --sign-key              sign a key
     --lsign-key             sign a key locally
     --edit-key              sign or edit a key
     --change-passphrase     change a passphrase
     --export                export keys
     --send-keys             export keys to a keyserver
     --receive-keys          import keys from a keyserver
     --search-keys           search for keys on a keyserver
     --refresh-keys          update all keys from a keyserver
     --import                import/merge keys
     --card-status           print the card status
     --edit-card             change data on a card
     --change-pin            change a card's PIN
     --update-trustdb        update the trust database
     --print-md              print message digests
     --server                run in server mode
     --tofu-policy VALUE     set the TOFU policy for a key

Options:

 -a, --armor                 create ascii armored output
 -r, --recipient USER-ID     encrypt for USER-ID
 -u, --local-user USER-ID    use USER-ID to sign or decrypt
 -z N                        set compress level to N (0 disables)
     --textmode              use canonical text mode
 -o, --output FILE           write output to FILE
 -v, --verbose               verbose
 -n, --dry-run               do not make any changes
 -i, --interactive           prompt before overwriting
     --openpgp               use strict OpenPGP behavior

(See the man page for a complete listing of all commands and options)

Examples:

 -se -r Bob [file]          sign and encrypt for user Bob
 --clear-sign [file]        make a clear text signature
 --detach-sign [file]       make a detached signature
 --list-keys [names]        show keys
 --fingerprint [names]      show fingerprints

Please report bugs to <https://bugs.gnupg.org>.


dput --help
Usage: dput [options] [host] <package(s).changes>
 Supported options (see man page for long forms):
   -c: Config file to parse.
   -d: Enable debug messages.
   -D: Run dinstall after upload.
   -e: Upload to a delayed queue. Takes an argument from 0 to 15.
   -f: Force an upload.
   -h: Display this help message.
   -H: Display a list of hosts from the config file.
   -l: Run lintian before upload.
   -U: Do not write a .upload file after uploading.
   -o: Only check the package.
   -p: Print the configuration.
   -P: Use passive mode for ftp uploads.
   -s: Simulate the upload only.
   -u: Don't check GnuPG signature.
   -v: Display version information.
   -V: Check the package version and then upload it.


apt-get --help
apt 2.0.5 (amd64)
Usage: apt-get [options] command
       apt-get [options] install|remove pkg1 [pkg2 ...]
       apt-get [options] source pkg1 [pkg2 ...]

apt-get is a command line interface for retrieval of packages
and information about them from authenticated sources and
for installation, upgrade and removal of packages together
with their dependencies.

Most used commands:
  update - Retrieve new lists of packages
  upgrade - Perform an upgrade
  install - Install new packages (pkg is libc6 not libc6.deb)
  reinstall - Reinstall packages (pkg is libc6 not libc6.deb)
  remove - Remove packages
  purge - Remove packages and config files
  autoremove - Remove automatically all unused packages
  dist-upgrade - Distribution upgrade, see apt-get(8)
  dselect-upgrade - Follow dselect selections
  build-dep - Configure build-dependencies for source packages
  satisfy - Satisfy dependency strings
  clean - Erase downloaded archive files
  autoclean - Erase old downloaded archive files
  check - Verify that there are no broken dependencies
  source - Download source archives
  download - Download the binary package into the current directory
  changelog - Download and display the changelog for the given package

See apt-get(8) for more information about the available commands.
Configuration options and syntax is detailed in apt.conf(5).
Information about how to configure sources can be found in sources.list(5).
Package and version choices can be expressed via apt_preferences(5).
Security details are available in apt-secure(8).
                                        This APT has Super Cow Powers.
```