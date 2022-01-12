[comment]: # "Auto-generated SOAR connector documentation"
# RIPE

Publisher: Splunk  
Connector Version: 2\.1\.2  
Product Vendor: RIPE  
Product Name: RIPE  
Product Version Supported (regex): "2017\.8\.\*"  
Minimum Product Version: 5\.0\.0  

This app integrates with RIPE to support investigative actions

[comment]: # " File: README.md"
[comment]: # "  "
[comment]: # "  Copyright (c) 2017-2022 Splunk Inc."
[comment]: # "  Licensed under the Apache License, Version 2.0 (the 'License');"
[comment]: # "  you may not use this file except in compliance with the License."
[comment]: # "  You may obtain a copy of the License at  "
[comment]: # "      http://www.apache.org/licenses/LICENSE-2.0   "
[comment]: # "  "
[comment]: # "  Unless required by applicable law or agreed to in writing, software distributed under"
[comment]: # "  the License is distributed on an 'AS IS' BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,"
[comment]: # "  either express or implied. See the License for the specific language governing permissions"
[comment]: # "  and limitations under the License."
[comment]: # ""
The app uses HTTP/ HTTPS protocol for communicating with the Ripe server. Below are the default
ports used by Splunk SOAR.

|         Service Name | Transport Protocol | Port |
|----------------------|--------------------|------|
|         http         | tcp                | 80   |
|         https        | tcp                | 443  |


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a RIPE asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | Base URL

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[lookup ip](#action-lookup-ip) - Queries RIPE for abuse counts associated with an IP  
[get email](#action-get-email) - Retrieves the associated abuse e\-mail  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'lookup ip'
Queries RIPE for abuse counts associated with an IP

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to lookup | string |  `ip`  `ipv6` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.build\_version | string | 
action\_result\.data\.\*\.cached | boolean | 
action\_result\.data\.\*\.data\.query\_endtime | string | 
action\_result\.data\.\*\.data\.query\_starttime | string | 
action\_result\.data\.\*\.data\.resource | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level1\.\*\.details | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level1\.\*\.prefix | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level1\.\*\.timelines\.\*\.endtime | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level1\.\*\.timelines\.\*\.starttime | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level2\.\*\.details | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level2\.\*\.prefix | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level2\.\*\.timelines\.\*\.endtime | string | 
action\_result\.data\.\*\.data\.sources\.uceprotect\-level2\.\*\.timelines\.\*\.starttime | string | 
action\_result\.data\.\*\.data\_call\_status | string | 
action\_result\.data\.\*\.data\_call\_name | string | 
action\_result\.data\.\*\.messages | string | 
action\_result\.data\.\*\.process\_time | numeric | 
action\_result\.data\.\*\.query\_id | string | 
action\_result\.data\.\*\.see\_also | string | 
action\_result\.data\.\*\.server\_id | string | 
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.status\_code | numeric | 
action\_result\.data\.\*\.time | string | 
action\_result\.data\.\*\.version | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get email'
Retrieves the associated abuse e\-mail

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to lookup | string |  `ip`  `ipv6` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.build\_version | string | 
action\_result\.data\.\*\.cached | boolean | 
action\_result\.data\.\*\.data\.abuse\_contacts\.\* | string |  `email` 
action\_result\.data\.\*\.data\.authoritative\_rir | string | 
action\_result\.data\.\*\.data\.earliest\_time | string | 
action\_result\.data\.\*\.data\.lastest\_time | string | 
action\_result\.data\.\*\.data\.parameters\.resource | string |  `ip`  `ipv6` 
action\_result\.data\.\*\.data\_call\_status | string | 
action\_result\.data\.\*\.data\_call\_name | string | 
action\_result\.data\.\*\.messages | string | 
action\_result\.data\.\*\.process\_time | numeric | 
action\_result\.data\.\*\.query\_id | string | 
action\_result\.data\.\*\.see\_also | string | 
action\_result\.data\.\*\.server\_id | string | 
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.status\_code | numeric | 
action\_result\.data\.\*\.time | string | 
action\_result\.data\.\*\.version | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 