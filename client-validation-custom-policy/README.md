# client-validation-custom-policy

1. Add the below profile in settings.xml to generate the required archetype for custom policy
<profile>
	<id>archetype-repository</id>
	<repositories>
		<repository>
			<id>archetype</id>
			<name>Mule Repository</name>
			<url>https://repository.mulesoft.org/nexus/content/repositories/public</url>
			<releases>
				<enabled>true</enabled>
				<checksumPolicy>fail</checksumPolicy>
			</releases>
			<snapshots>
				<enabled>true</enabled>
				<checksumPolicy>warn</checksumPolicy>
			</snapshots>
		</repository>
	</repositories>
</profile>

2. Run the below command to create the maven archetype project for custom policy
mvn -Parchetype-repository archetype:generate ^
-DarchetypeGroupId=org.mule.tools ^
-DarchetypeArtifactId=api-gateway-custom-policy-archetype ^
-DarchetypeVersion=1.2.0 ^
-DgroupId=<org-id> ^
-DartifactId=<policy-name> ^
-Dversion=1.0.0 ^
-Dpackage=mule-policy

<ord-id> = Anypoint platform organization id
<policy-name> = Custom policy name

3. mvn clean deploy - To upload the custom policy to anypoint exchange.

