Helpdesk Escalation Note \& Scope Boundary

Ticket ID: CVNP1606-W06-006

Affected User: Emily Park

Impact Level: High High — employee is blocked from all ACME resources during working hours.

Technician: Tier-1 Help Desk Support



1\. Tier-1 Scope 

The following diagnostic and corrective actions are allowed within Tier-1 boundaries:

* ipconfig /release + /renew
* ipconfig /flushdns
* Network profile: Public → Private
* Restart DHCP/DNS client service
* Document + write user instructions



2\. Escalation Scope (Network Team Handoff)

The following conditions exceed Tier-1 permissions and must be formally escalated. Do not attempt these things as a Tier-1 Tech.

* DHCP scope / reservation changes
* DNS record / forwarder changes
* Firewall rules on switches/routers
* VPN gateway configuration
* Home router / ISP mode

