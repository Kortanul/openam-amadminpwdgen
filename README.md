# AmAdminPwdGen

**Requires Java 1.8**

This tool generates the password hash for the amadmin account in OpenAM without the need for ssoadm to be installed. The amadmin password hash is located in a sunKeyValue attribute here:

`ou=amAdmin,ou=users,ou=default,ou=GlobalConfig,ou=1.0,ou=sunIdentityRepositoryService,ou=services,dc=openam,dc=forgerock,dc=org`

It is encrypted with the deployment server key, which is located here:

`ou=servername,ou=com-sun-identity-servers,ou=default,ou=GlobalConfig,ou=1.0,ou=iPlanetAMPlatformService,ou=services,dc=openam,dc=forgerock,dc=org
`

To use the tool, first build it:

`javac AmAdminPwdGen.java`

Then execute it, providing the server key (-k) and plain text version of your password (-p) as command line options:

`java AmAdminPwdGen -p somepass -k Cy+0NrV1234/iqViszpAhO1BBckO1234`

