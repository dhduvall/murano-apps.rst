# Copyright 2015 Oracle and/or its affiliates. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

Oracle PDB Connector (package)
Package name:  com.oracle.db.muranoPdb.OraclePDB


Description:
Oracle PDB Connector is a Murano application that provides OpenStack cloud users with means for self-service provisioning of Oracle Database 12c and Oracle Multitenant Pluggable DataBases (PDBs). 

This is an unsupported technology preview release not intended for use in production environments.

Supported OpenStack Releases
Juno, Kilo

Author
Contact: Eric Saxe
Company: Oracle Inc.

Depends On
1. Pre-Installed Oracle Database 12c with Oracle Multitenant option on Oracle Solaris 11.2.

The following environment variables need to be set:
Create a file /etc/oraenv/ora_env.sh
Set read/write permissions for user 'oracle'

Set the following environment variables in /etc/oraenv/ora_env.sh
 
ORACLE_BASE      # The base directory of Oracle database installation
ORACLE_HOME = $ORACLE_BASE/<oracle12c directory> 
ORACLE_SID       # Oracle System Identifier
ORADATA          # Oracle application directory e.g. /u01/app/oracle/oradata
ORACLE_USER_HOME # Home directory of user oracle


Create a file /etc/oraenv/orapwd
Set read/write permissions for user 'oracle'
Enter the username and password admin and system users:
Set the following variables:
ADMIN_USER=
SYSTEM_USER=
ADMIN_PWD=
SYSTEM_USER_PWD=


2. Latest murano-agent.

murano-agent setup instructions
- Download the latest tarball of murano-agent and it's dependent packages on the node where Oracle 12c is running.
- Install each of the package by doing the following,
  # tar -zxvf <package>.tar.gz
  # cd <package>
  # ./setup build
  # ./setup install

- For murano-agent, a binary "muranoagent" will be copied into /usr/bin directory
- Setup the murano-agent by copying and editing the sample conf file as /etc/murano/agent.conf
- Edit /etc/murano/agent.conf and set enable_dynamic_result_queue to True in the DEFAULT section. Set input_queue with queue information from the muranoclient
- Start the murano-agent,
  # /usr/bin/muranoagent --config-file /etc/murano.conf 


Attributes
Package URL: http://storage.apps.openstack.org/apps/io.murano.apps.oracle.pdbconnector.zip
Source URL: https://github.com/openstack/murano-apps/tree/master/OraclePDBConnector/package
