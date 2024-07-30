# Oopsies

I went above and beyond to contact the person behind `buzzster.co.uk`, but every method has failed. I have reached out multiple times to the domain registrar and filled in a form in order to contact the real domain holder, I have looked everywhere to find the person whom is the actual owner. I got their username and full name (as printed on the identification papers) but no way to reach out without revealing my identity. Which is something I do not want, sorry. That is the sole reason I didn't call the number on the `buzzster.co.uk` website.

### What is going on?

1. It turns out that someone (I won't call out names) forgot to pay the invoice for their VPS that previously ran `mail.buzzster.co.uk`. As a consequence, the provider cancelled the VPS and freed up the IP address.
2. When I purchased a new VPS to run a mailserver on, with the exact same company, it appointed me the IP address that was formerly in use by `mail.buzzster.co.uk`. I noticed this, because there were all kinds of failed delivery attempts at my new mailserver.
3. I investigated this issue for a bit and found out that they were trying to deliver to `kevv(something)@buzzstar.co.uk`, which failed to to a SAN mismatch on the certificate.
4. Further diving in revealed the hostname and that it was actually still setup in the DNS as the A record for `mail.buzzster.co.uk`.

### Okay, how to fix this?

I have no bad intentions here, at all. I just want to have the person responsible for `buzzster.co.ik` to change their MX record to something that stops filling up my MTA logs with nonsense. If you are the holder/owner of `buzzster.co.uk`, this is how you can fix it:

1. Grab a cup of coffee (or another hot beverage),
2. Get a new mailserver, or subscribe to a hosted mail provider,
3. Change the MX record for `buzzster.co.uk` and remove or change the (current) IP for `mail.buzzster.co.uk`,
4. Reset the Github account after the DNS is propagated and subsequentually delete this repository.

That is all. Thank you for understanding. Hope I did not get you upset - you should have prevented this in the first place... And again, I have no bad intention here.

### EOF
