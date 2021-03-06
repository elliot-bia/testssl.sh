
### Certificate stores

The certificate trust stores were retrieved from

* **Linux:** Copied from an up-to-date Debian Linux machine
* **Mozilla:** https://curl.haxx.se/docs/caextract.html
* **Java:** JRE keystore pulled + extracted with keytool from a Linux machine from  $JAVA_HOME/jre/lib/security/cacerts
* **Microsoft:** Following command pulls all certificates from Windows Update services: ``CertUtil -syncWithWU -f -f . `` (see also http://aka.ms/RootCertDownload, https://technet.microsoft.com/en-us/library/dn265983(v=ws.11).aspx#BKMK_CertUtilOptions).
* **Apple:**
    1. __System:__ from Apple OS X keychain app.  Open Keychain Access utility, i.e.
  In the Finder window, under Favorites --> "Applications" --> "Utilities"
  (OR perform a Spotlight Search for Keychain Access)
  --> "Keychain Access" (2 click). In that window --> "Keychains" --> "System"
  --> "Category" --> "All Items"
  Select all CA certificates except for Developer ID Certification Authority,  "File" --> "Export Items"
    2. __Internet:__ Pick the latest subdir from https://opensource.apple.com/source/security_certificates/. They are in DER format despite their file extension.

Google Chromium uses basically the trust stores above, see https://www.chromium.org/Home/chromium-security/root-ca-policy.

If you want to test against e.g. a company internal CA you want to avoid warnings from the certificate stores here it's recommended to use ``ADDITIONAL_CA_FILES=<companyCA.pem ./testssl.sh <your cmdline>``. (The former mechanism was to put the company root CA certificate here.)


#### Further files

* ``tls_data.txt`` contains lists of cipher suites and private keys for sockets-based tests

* ``cipher-mapping.txt`` contains information about all of the cipher suites defined for SSL/TLS

* ``ca_hashes.txt`` is used for HPKP test in order to have a fast comparison with known CAs. Use
   ``~/utils/create_ca_hashes.sh`` for an update

* ``common-primes.txt`` is used for LOGJAM and the PFS section

* ``client-simulation.txt`` / ``client-simulation.wiresharked.txt`` are as the names indicate data for the client simulation.
  The first one is derived from ``~/utils/update_client_sim_data.pl``, and manually edited to sort and label those we don't want.
  The second file provides more client data retrieved from wireshark captures and some instructions how to do that yourself.
