# Background

This project is an assignment from a pre-employment test for the company Ad Hoc titled "Provision".

# Provision - Comments

Overall there is only one notable aspect for this excercise.

### Nginx - SSL protocols

Initially I tried adding the following to `nginx.conf`:
`ssl_protocols TLSv1.2 TLSv1.3;`

But `nginx` would fail to start and the following message clearly stated that `TLSv1.3` was the issue:
`nginx: [warn] invalid value "TLSv1.3" in /etc/nginx/nginx.conf:75`

After a look at the VM and some investigation, I found the version of `nginx` to be the culprit. The latest available package for `CentOS 6.9` is `nginx/1.10.3` and only since `nginx/1.13` support has been added for `TLSv1.3`.