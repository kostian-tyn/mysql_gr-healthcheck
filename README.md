# MySQL Group Replication healthcheck script for ExaBGP

The script based on the original one: https://github.com/Exa-Networks/exabgp/blob/3.4/lib/exabgp/application/healthcheck.py

It makes persistent connection to database and uses SQL query to check DB node role:

\'SELECT viable_candidate, read_only, transactions_behind FROM sys.gr_member_routing_candidate_status\'

You have to add the view previously - https://gist.github.com/lefred/6f79fd02d333851b8d18f52716f04d91

The script looks for primary member by default. If you need to check secondary one, put "readonly" option to configuration file.
