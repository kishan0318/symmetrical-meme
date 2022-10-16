# symmetrical-meme
In case You have to work on 2 projects at same time and both having 2 diffrent Databases connected , in which one is Postgres ,Then you can change the port no. of postgres with help of following steps...read all points first then apply: 

How to change the Port no. of your postgresSql:
[In case you have to work with MySql and Postgres both you can change the port no. of postgres and use both at same time]

I have changed the port no. of Postgres(5432 to 5433) all you have to do is:

1.Go to follow the path: 'C:\Program Files\PostgreSQL\12\data'
2.There should be a file called "postgresql.conf" open with Notepad 
3. find 'port=5432' written anywhere in that file and now change the 5432 to > '5433'.
4. Then you have to restart the  service of postgres , that can be done by "WINkey+r" then type "services.msc" find postgres and then stop it an start it. [if does not work then jump to 5 else jump to 6]
5. In some systems "services.msc" will not work because of windows privacy in that case and if poin 4 haven't worked: 
    [If already set the variable path of PGDATA jump to 6th  point.]
     a. Searching for env will show Edit environment variables for your account
     b. Select Environment Variables
     c.  From the System Variables box select PATH
     d. Click New (to add new path)
     e. Add valiable name as 'PGDATA' and variable value as 'C:\Program Files\PostgreSQL\12\data'.
6. Now restart the Postgres requires restart, use the command in CMD "pg_ctl restart" to restart it.
7. Now open "SQL Shell (psql)" then it will ask for "port[5432]: " type 5433 .It will now work.

for PgAdmin>
8. Open PgAdmin>servers>PostgreSql12>  it will ask open in port 5432 use edit button and change port no. to 5433.

It will also work now.

If using django framework for your project and using postgres ...try checking your port no. on your setting.py file and run the command "postgres -p 5433" on cmd while working on the same project:
eg:
      DATABASES = {
          'default': {
              'ENGINE': 'django.contrib.gis.db.backends.postgis',
              'NAME':'Your_db_name_here',
              'USER':'Your_user_here',
              'PASSWORD':'Your_password_here',
              'HOST':'localhost',
              'PORT':'5433',
          }
      }

Thank You!!!
