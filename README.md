# github-invitation-hijack

It's possile to anyone hicjak Github organization invitation, official statment from Github wast that its "intended". Since, me as security resarcher find this kind of bug should be considered dangerous, especially if the worse happens then publicity should be aware of that and keep in mind when they deal with "organization" in Github.

Below is my report to Github:

## Description:
When organization owner invites new users to his organization, user will receive an email with the invitation link. This link has 0 security to ensure that person who is using link is person who should be using. This means that anyone with the link can hijack invitation and become organization (illegal) member. In real life dedicated attacks are built up step by step and this link can be acquired via phishing for example.

Possible solution or fix is recommended to have check does the person github account who is using link corresponds to invited accounts.

**Exmaple:**

```
if (inviteAccount != currentAccount ) {
    print "You are not authorized to use this resource";
}
```

## Steps To Reproduce:
Organization owner (adds new seat if needed) and invites new member.
New member receives invitation link to his email.
Attacker acquires link (how this link is leaked is not related to github security) and has open session in his web browser with his account. Attacker clicks on link and he is added to organization.
Profit - in worst case attacker gained owner role and removes other users and owners
Impact
If i found this issue the link what i got was supposed to make invited user to owner of organization. All this happened after business hours which means that engineers are no "online". As an attacker i could remove quickly other owners and members and steal the code or do whatever any harm to organization. Most of today startups are relaying GitHub service and losing their source code means basically bankruptcy.

---

Official statemnet from Gtihub:

> Hi,
>Thanks for the submission! We have reviewed your report and validated your findings. After internally assessing the finding we have determined is is a known low risk issue. It is intended that the token in the organization-invite email be redeemable by the recipient, regardless of the account they are authenticated as. We are aware of the risks associated with this behavior. As a result, this is not eligible for reward under the Bug Bounty program.
>Best regards and happy hacking!
