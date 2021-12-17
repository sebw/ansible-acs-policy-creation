# Create new policies in ACS with Ansible

## Ansible

Create your Ansible Vault with those variables:

```yaml
vaulted_acs_host: <your-acs-host>
vaulted_acs_user: <your-acs-user>
vaulted_acs_pass: <your-acs-pass>
```

Run your playbook and pass the CVE reference:

```bash
ansible-playbook --ask-vault-pass playbook.yml -e cve=CVE-2021-44228
```

Rationale, remediation, etc. can also be defined.

## Ansible Automation Platform (AAP)

This playbook can be used with Ansible Automation Platform and take advantage of surveys.

![](https://raw.githubusercontent.com/sebw/ansible-acs-policy-creation/master/aap_survey.png)

![](https://raw.githubusercontent.com/sebw/ansible-acs-policy-creation/master/aap_job.png)
