certificate-authority
=====================

Import my public CA certificate to trust certificates that I have
signed.

Examples
--------

## Debian

The following code should be sufficient to update the CA certs.

```
$ cp ikelewis_ca_cert.crt /usr/local/share/ca-certificates/
$ update-ca-certificates
```

If you experience problems with tools like wget or git, check that the
/etc/ca-certificates file was actually updated.

```
$ cat /etc/ssl/certs/ca-certificates.crt | grep MIIDhzCCAm+g

MIIDhzCCAm+gAwIBAgIJANg0S6lWK1tNMA0GCSqGSIb3DQEBCwUAMFoxCzAJBgNV
```

If no output appears, the certificate may have been copied to the
wrong location.

## Firefox

1) Go to Edit ->
         Preferences ->
	 Advanced ->
	 View Certificates ->
	 Import

2) Select '/usr/local/share/ca-certificates/ikelewis_ca_cert.crt'.

3) Check the three trust boxes.

4) Click 'OK'