# zabbix-templates
Template allows to monitor your CISCO ESA ( IRONPORT ).  number of active recipients, number of completed recipietns per minute, number of injected (recieved by esa) messages per minute, number of connections and so on.
For now there is no triggers.

Installation: 
1) import the template, 
2) create read_only_operator user in your ESA, 
3) create and fill in value macros in zabbix ESA host: {$IRP_LOGIN} for login and {$IRP_PASS} for password (both created on step 2)
4) link imported template to ESA host

Default update interval is 5 min. you can chage it in "Get_Ironport_xml_status" item.

Tempalate contains 28 items.
"HTTP agent" item (Get_Ironport_xml_status) reads xml status page from ESA (https://{HOST.IP}/xml/status)
and 27 dependet items, using preproceccing and XML Path to get items from XML:
- 5xx_hard_bounced_recips
- active_recips
- completed_recips
- completed_recips_last_1_min
- conn_in
- conn_out
- deleted_recips
- delivered_recips
- delivered_recips_last_1_min
- dns_hard_bounced_recips
- dropped_msgs
- expired_hard_bounced_recips
- filter_hard_bounced_recips
- gen_bounce_recips
- global_unsub_hits
- hard_bounced_recips
- hard_bounced_recips_last_1_min
- inj_msgs
- inj_msgs_last_1_min
- inj_recips
- inj_recips_last_1_min
- kbytes_in_policy_virus_outbreak_quarantine
- msgs_in_policy_virus_outbreak_quarantine
- other_hard_bounced_recips
- rejected_recips
- soft_bounced_evts
- soft_bounced_evts_last_1_min
