Server Outage Incident report
By Hammed Yakub

26th February 2024, we experienced server outage on all our server infrastructure which resulted in our clients inability to use our services and we sincerely apologize for the financial loss our clients have incurred during this period.


Issue Summary

On 26th February 2024, we experienced a server outage (downtime) on all of our server infrastructure which lasted for 48 minutes. As a result of this, our clients experienced a http 500 error which had a 100% impact on their business as they were unable to access our services. The root cause was not properly testing out all implemented upgrades before pushing to production servers.


Timeline (all time in GMT + 1)

Time (GMT + 1)	Actions
7:25 PM	Upgrades implementation begins
8:00PM	Server Outage begins
8:00PM	Pagers alerted on-call team
8:10PM	On-call team acknowledgement
8:25PM	Rollback initiation begins
8:30PM	Successful rollback
8:32PM	Server restart initiated
8:42AM	100% of traffic back online


Root cause

At 8:55PM (GMT + 1) server upgrade was initiated across all our production servers without first releasing on our test environments and performing all necessary unit testing. Part of the upgrade been shipped to production server required an authentication from a 3rd party software, this new implementation is not supported on the current version present on our servers which resulted in the downtime experienced. We were able to resolve this quickly by first performing a rollback the severs previous state thereafter upgrading the current version on our servers.


Preventive measures

Pushing all intended changes 1st to our test environments before shipping to life server.
Increase the performance metrics threshold to alert on-call engineers on the event of possible server crash. Revamp these and make it more convincing and genuine 
