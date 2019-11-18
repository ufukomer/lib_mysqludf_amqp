ACLOCAL_AMFLAGS = -I m4

EXTRA_DIST = README.md CONTRIBUTING.md installdb.sql uninstalldb.sql

lib_LTLIBRARIES = lib_mysqludf_amqp.la
lib_mysqludf_amqp_la_SOURCES = lib_mysqludf_amqp.h lib_mysqludf_amqp_info.c send.h send.c lib_mysqludf_amqp_sendjson.c lib_mysqludf_amqp_sendstring.c uuid.h uuid.c
lib_mysqludf_amqp_la_CFLAGS = -DMYSQL_SERVER @MYSQL_CFLAGS@ @RABBITMQ_CFLAGS@
lib_mysqludf_amqp_la_LDFLAGS = -module -avoid-version -no-undefined @MYSQL_LDFLAGS@ @RABBITMQ_LIBS@

installdb:
	mysql -u root -p$(MYSQL_PASSWORD) < ./installdb.sql

uninstalldb:
	mysql -u root -p$(MYSQL_PASSWORD) < ./uninstalldb.sql

version:
	mysql -u root -p$(MYSQL_PASSWORD) --execute="SELECT lib_mysqludf_amqp_info();"
