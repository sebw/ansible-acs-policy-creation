# Create new policies in ACS with Ansible

## Challenge

We want to automate the creation of policies in Red Hat Advanced Cluster Security for Kubernetes.

There's an API endpoint for the task so it can be automated with Ansible.

## Ansible

Create your Ansible Vault with those variables:

```yaml
vaulted_acs_host: <your-acs-host>
vaulted_acs_token: <your-acs-API-token>
```

The ACS API token can either have the Admin role or, if you prefer, a custom role with read/write permission to the /policies API endpoint.  More info can be found [here](https://docs.openshift.com/acs/3.67/cli/getting-started-cli.html#cli-authentication_cli-getting-started).


Run your playbook and pass the CVE reference:

```bash
ansible-playbook --ask-vault-pass playbook.yml -e cve=CVE-2021-44228
```

Rationale, remediation, etc. can also be defined.

## Ansible Automation Platform (AAP)

This playbook can also be used with Ansible Automation Platform and take advantage of surveys.

![](https://raw.githubusercontent.com/sebw/ansible-acs-policy-creation/master/aap_survey.png)

![](https://raw.githubusercontent.com/sebw/ansible-acs-policy-creation/master/aap_job.png)

## Output

![](https://raw.githubusercontent.com/sebw/ansible-acs-policy-creation/master/acs_policy.png)