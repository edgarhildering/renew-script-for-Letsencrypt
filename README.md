# renew script for Letsencrypt
 renew script for Letsencrypt
 
# Introduction
 Let's Encrypt is extremely popular when it comes to generating a certificate. This makes secure communication within everyone's reach.
Let's-Encrypt certificates have a validity of 90 days. It is possible to renew the certificate from 30 days before it expires.
This collection of scripts ensures that, unlike checking daily with crontab, a renew request is made 25 days before the expiration.

# Efficient renewal
> Certbot is a free, open source software tool for automatically using Let's Encrypt certificates on manually-administered websites to enable HTTPS.
This is according to the certbot site. I also have chosen this tool. It has a renew-command that takes care of the renewal of your certificate. Certbot allows you to renew the certificate even 30 days before it expires. The renewal is the responsibility of the user, i.e. YOU. On the internet the common method for renewal is to call certbot renewal with crontab. I admit: this is a very simple and straightforward approach, since certbot will skip the renewal if it is not yet due. However, if you check it daily after creation, it is likely that your attempt will be skipped about 60 times. I have no insight into the precise operation of certbot's renew command, but when the renewal is skipped, the renew command does show a spike in both CPU load and I/O activity. 
Certbot can inform you about the validity period of a certificate. This allows you to calculate the earliest moment the certificate can be renewed. As stated, this can be a maximum of 30 days before the certificate expires. If you know when the earliest moment is that the renew command actually has an effect, you could schedule a renew job at that specific time, which is much more efficient and just as effective.




