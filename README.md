# pbasu-OracleDB-tutorials

# Oracle Password Expire & Locked - RESET
* https://www.krenger.ch/blog/oracle-workaround-for-password-unexpire/
* http://www.ateam-oracle.com/avoiding-and-resetting-expired-passwords-in-oracle-databases
* https://blogs.oracle.com/sql/how-to-fix-ora-28002-the-password-will-expire-in-7-days-errors
* https://daviewning.wordpress.com/2015/09/17/set-oracle-user-password-never-expired/
* https://shaileshpurani.wordpress.com/2012/01/30/verify-oracle-user-password-expiry-date/
* 
* 
* 
* 
* 



ALTER PROFILE DEFAULT LIMIT PASSWORD_LIFE_TIME UNLIMITED;
select * from dba_profiles;

select username,account_status from dba_users where account_status like '%EXPIRED%' or account_status like '%LOCKED%';

select * from dba_users;


select 'ALTER USER '|| USERNAME || ' account unlock;' from dba_users where ACCOUNT_STATUS like '%LOCKED%';
select 'ALTER USER '|| USERNAME || ' identified by values ''' || spare4 || ''';' from dba_users,user$ where ACCOUNT_STATUS like '%EXPIRED%' and USERNAME=NAME;


