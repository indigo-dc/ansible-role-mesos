cms_config Role
=========

Configure CVMFS,  ENV Variables,  TFC, Proxy, etc for CMS


Role Variables
--------------

- `cms_config_cvmfs_http_proxy` (default: "http://cream-bdii.pg.infn.it:3128")
- `cms_config_cvmfs_repositories` (default: "cms")
- `cms_config_certificate_path` (default: "/root/.globus/spiga_x509up_u16858")
- `cms_config_cms_local_site` (default: "T3_IT_Spiga")
- `cms_config_mysquid` (default: "http://cream-bdii.pg.infn.it:3128")
- `cms_config_stageoutsite` (default: "T1_IT_CNAF_Disk")
- `cms_config_stageoutserver` (default: "storm-fe-cms.cr.cnaf.infn.it")
- `cms_config_stageoutprefix` (default: "srm://storm-fe-cms.cr.cnaf.infn.it:8444/srm/managerv2?SFN=/cmsdisk/")
- `cms_config_vomsproxydir` (default: "/root/.globus")


Dependencies
------------

None

Example Playbook
----------------

This is an example of how to use `cms_config` role:

    - hosts: servers
      roles:
         - { role: indigo-dc.cms_config, cms_config_cms_local_site: "MY_SITE" }

License
-------

Apache Licence v2 [1]

[1] http://www.apache.org/licenses/LICENSE-2.0


Author Information
------------------

marica.antonacci@ba.infn.it

daniele.spiga@pg.infn.it
