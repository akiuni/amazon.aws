.. _amazon.aws.aws_secret_lookup:


*********************
amazon.aws.aws_secret
*********************

**Look up secrets stored in AWS Secrets Manager.**



.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Look up secrets stored in AWS Secrets Manager provided the caller has the appropriate permissions to read the secret.
- Lookup is based on the secret's *Name* value.
- Optional parameters can be passed into this lookup; *version_id* and *version_stage*



Requirements
------------
The below requirements are needed on the local Ansible controller node that executes this lookup.

- python >= 3.6
- boto3 >= 1.18.0
- botocore >= 1.21.0


Parameters
----------

.. raw:: html

    <table  border=0 cellpadding=0 class="documentation-table">
        <tr>
            <th colspan="1">Parameter</th>
            <th>Choices/<font color="blue">Defaults</font></th>
                <th>Configuration</th>
            <th width="100%">Comments</th>
        </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>_terms</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">-</span>
                         / <span style="color: red">required</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Name of the secret to look up in AWS Secrets Manager.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>aws_access_key</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                                <div>env:EC2_ACCESS_KEY</div>
                                <div>env:AWS_ACCESS_KEY</div>
                                <div>env:AWS_ACCESS_KEY_ID</div>
                    </td>
                <td>
                        <div>The AWS access key to use.</div>
                        <div style="font-size: small; color: darkgreen"><br/>aliases: aws_access_key_id</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>aws_profile</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                                <div>env:AWS_DEFAULT_PROFILE</div>
                                <div>env:AWS_PROFILE</div>
                    </td>
                <td>
                        <div>The AWS profile</div>
                        <div style="font-size: small; color: darkgreen"><br/>aliases: boto_profile</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>aws_secret_key</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                                <div>env:EC2_SECRET_KEY</div>
                                <div>env:AWS_SECRET_KEY</div>
                                <div>env:AWS_SECRET_ACCESS_KEY</div>
                    </td>
                <td>
                        <div>The AWS secret key that corresponds to the access key.</div>
                        <div style="font-size: small; color: darkgreen"><br/>aliases: aws_secret_access_key</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>aws_security_token</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                                <div>env:EC2_SECURITY_TOKEN</div>
                                <div>env:AWS_SESSION_TOKEN</div>
                                <div>env:AWS_SECURITY_TOKEN</div>
                    </td>
                <td>
                        <div>The AWS security token if using temporary access and secret keys.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>bypath</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">boolean</span>
                    </div>
                    <div style="font-style: italic; font-size: small; color: darkgreen">added in 1.4.0</div>
                </td>
                <td>
                        <b>Default:</b><br/><div style="color: blue">"no"</div>
                </td>
                    <td>
                    </td>
                <td>
                        <div>A boolean to indicate whether the parameter is provided as a hierarchy.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>join</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">boolean</span>
                    </div>
                </td>
                <td>
                        <b>Default:</b><br/><div style="color: blue">"no"</div>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Join two or more entries to form an extended secret.</div>
                        <div>This is useful for overcoming the 4096 character limit imposed by AWS.</div>
                        <div>No effect when used with <em>bypath</em>.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>nested</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">boolean</span>
                    </div>
                    <div style="font-style: italic; font-size: small; color: darkgreen">added in 1.4.0</div>
                </td>
                <td>
                        <b>Default:</b><br/><div style="color: blue">"no"</div>
                </td>
                    <td>
                    </td>
                <td>
                        <div>A boolean to indicate the secret contains nested values.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>on_deleted</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                    <div style="font-style: italic; font-size: small; color: darkgreen">added in 2.0.0</div>
                </td>
                <td>
                        <ul style="margin: 0; padding: 0"><b>Choices:</b>
                                    <li><div style="color: blue"><b>error</b>&nbsp;&larr;</div></li>
                                    <li>skip</li>
                                    <li>warn</li>
                        </ul>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Action to take if the secret has been marked for deletion.</div>
                        <div><code>error</code> will raise a fatal error when the secret has been marked for deletion.</div>
                        <div><code>skip</code> will silently ignore the deleted secret.</div>
                        <div><code>warn</code> will skip over the deleted secret but issue a warning.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>on_denied</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                        <ul style="margin: 0; padding: 0"><b>Choices:</b>
                                    <li><div style="color: blue"><b>error</b>&nbsp;&larr;</div></li>
                                    <li>skip</li>
                                    <li>warn</li>
                        </ul>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Action to take if access to the secret is denied.</div>
                        <div><code>error</code> will raise a fatal error when access to the secret is denied.</div>
                        <div><code>skip</code> will silently ignore the denied secret.</div>
                        <div><code>warn</code> will skip over the denied secret but issue a warning.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>on_missing</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                        <ul style="margin: 0; padding: 0"><b>Choices:</b>
                                    <li><div style="color: blue"><b>error</b>&nbsp;&larr;</div></li>
                                    <li>skip</li>
                                    <li>warn</li>
                        </ul>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Action to take if the secret is missing.</div>
                        <div><code>error</code> will raise a fatal error when the secret is missing.</div>
                        <div><code>skip</code> will silently ignore the missing secret.</div>
                        <div><code>warn</code> will skip over the missing secret but issue a warning.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>region</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">string</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                                <div>env:EC2_REGION</div>
                                <div>env:AWS_REGION</div>
                    </td>
                <td>
                        <div>The region for which to create the connection.</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>version_id</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">-</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Version of the secret(s).</div>
                </td>
            </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="parameter-"></div>
                    <b>version_stage</b>
                    <a class="ansibleOptionLink" href="#parameter-" title="Permalink to this option"></a>
                    <div style="font-size: small">
                        <span style="color: purple">-</span>
                    </div>
                </td>
                <td>
                </td>
                    <td>
                    </td>
                <td>
                        <div>Stage of the secret version.</div>
                </td>
            </tr>
    </table>
    <br/>




Examples
--------

.. code-block:: yaml

    - name: lookup secretsmanager secret in the current region
       debug: msg="{{ lookup('amazon.aws.aws_secret', '/path/to/secrets', bypath=true) }}"

     - name: Create RDS instance with aws_secret lookup for password param
       rds:
         command: create
         instance_name: app-db
         db_engine: MySQL
         size: 10
         instance_type: db.m1.small
         username: dbadmin
         password: "{{ lookup('amazon.aws.aws_secret', 'DbSecret') }}"
         tags:
           Environment: staging

     - name: skip if secret does not exist
       debug: msg="{{ lookup('amazon.aws.aws_secret', 'secret-not-exist', on_missing='skip')}}"

     - name: warn if access to the secret is denied
       debug: msg="{{ lookup('amazon.aws.aws_secret', 'secret-denied', on_denied='warn')}}"

     - name: lookup secretsmanager secret in the current region using the nested feature
       debug: msg="{{ lookup('amazon.aws.aws_secret', 'secrets.environments.production.password', nested=true) }}"
       # The secret can be queried using the following syntax: `aws_secret_object_name.key1.key2.key3`.
       # If an object is of the form `{"key1":{"key2":{"key3":1}}}` the query would return the value `1`.
     - name: lookup secretsmanager secret in a specific region using specified region and aws profile using nested feature
       debug: >
        msg="{{ lookup('amazon.aws.aws_secret', 'secrets.environments.production.password', region=region, aws_profile=aws_profile,
        aws_access_key=aws_access_key, aws_secret_key=aws_secret_key, nested=true) }}"
       # The secret can be queried using the following syntax: `aws_secret_object_name.key1.key2.key3`.
       # If an object is of the form `{"key1":{"key2":{"key3":1}}}` the query would return the value `1`.
       # Region is the AWS region where the AWS secret is stored.
       # AWS_profile is the aws profile to use, that has access to the AWS secret.



Return Values
-------------
Common return values are documented `here <https://docs.ansible.com/ansible/latest/reference_appendices/common_return_values.html#common-return-values>`_, the following are the fields unique to this lookup:

.. raw:: html

    <table border=0 cellpadding=0 class="documentation-table">
        <tr>
            <th colspan="1">Key</th>
            <th>Returned</th>
            <th width="100%">Description</th>
        </tr>
            <tr>
                <td colspan="1">
                    <div class="ansibleOptionAnchor" id="return-"></div>
                    <b>_raw</b>
                    <a class="ansibleOptionLink" href="#return-" title="Permalink to this return value"></a>
                    <div style="font-size: small">
                      <span style="color: purple">-</span>
                    </div>
                </td>
                <td></td>
                <td>
                            <div>Returns the value of the secret stored in AWS Secrets Manager.</div>
                    <br/>
                </td>
            </tr>
    </table>
    <br/><br/>


Status
------


Authors
~~~~~~~

- Aaron Smith (!UNKNOWN) <ajsmith10381@gmail.com>


.. hint::
    Configuration entries for each entry type have a low to high priority order. For example, a variable that is lower in the list will override a variable that is higher up.
