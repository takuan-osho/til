# OpenSSL Tips

## Check when SSL certificate is expired

```
openssl s_client -connect some.cloudfront.net:443 < /dev/null 2> /dev/null | openssl x509 -text | grep Not
            Not Before: Nov 22 00:00:00 2017 GMT
            Not After : Nov 21 12:00:00 2018 GMT
```

refs. https://qiita.com/moonphase/items/a3a0937f77494e62213c (in Japanese)

## Fetch SSL certificate

```
echo | openssl s_client -connect some.cloudfront.net:443 -showcerts 2>&1 | sed --quiet '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > some.cloudfront.net.crt
```