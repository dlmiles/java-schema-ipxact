
[![CI-Gradle-build](https://github.com/dlmiles/java-schema-ipxact/actions/workflows/build.yml/badge.svg)](https://github.com/dlmiles/java-schema-ipxact/actions/workflows/build.yml)


## IP-XACT &trade; JAXB consumable Schema for Java.

This Gradle project produces Maven artifacts for easy consumption providing access
to the schemas with the JAXB Java APIs.

Due to the versatility of the Gradle plugin the project is able to generate for almost all possible
permutations of JAXB specification version, JVM bytecode compatibility and package namespace
(javax.xml.bind, jakarta.xml.bind).


#### Current project build requirements:

* Java 8+, Gradle 6.5+

A couple of Gradle plugins are on the edge of their Java 8 support (both plugins are used in the WSDL subprojects) :

group: 'net.sf.saxon', name: 'Saxon-HE', version: '11.5'
 * 11.5 JDK8 (this is configured at this time)
 * 12.0+ JDK11 (this is not yet considered stable)

id 'com.intershop.gradle.wsdl' version '3.2.2'
 * 3.2.2 JDK8 (this is configured at this time)
 * 3.3.0+ JDK11


#### Current project deliverables target:

* JAXB 2.2 (using XJC 2.4.x, Java 8, javax namespace)
* JAXB 2.3 (using XJC 4.0.x, Java 8, javax namespace)
* JAXB 3.0 (using XJC 4.0.x, Java 8, jakarta namespace)

Targets can be changed with the toplevel gradle.properties file via configuration
options indicated in the file, just activate by making a change of commenting.

You may be able to download a ZIP of the Maven M2 publish deliverables directly
from the Github Action area of this project.


#### Accessing the Github hosted Maven 2 Repository from your Gradle project

To use the Maven 2 repository in your gradle project the following snippet
may work for you.

```
// Gradle Groovy DSL
repositories {
    maven {
        // url 'https://dlmiles.github.io/java-schema-ipxact/maven2'
        url 'https://maven.pkg.github.com/dlmiles/java-schema-ipxact'
        content {
            // this repository *only* contains artifacts for specific groups
            includeGroup 'com.github.dlmiles.java.schema.ipxact'
            includeGroup 'com.github.dlmiles.java.schema.ipxact.jaxb2_2'
            includeGroup 'com.github.dlmiles.java.schema.ipxact.jaxb2_3'
            includeGroup 'com.github.dlmiles.java.schema.ipxact.jaxb3_0'
        }
    }
}

dependencies {
    implementation 'com.github.dlmiles.java.schema.ipxact.jaxb3_0:ipxact-1685-2014:1.0-SNAPSHOT'
}
```


#### The schemas covered by this project:

<table>
    <thead>
        <tr>
            <td><em>Subproject name</em></td>
            <td>XSD</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td><em>ipxact-1685-2014</em></td>
        <td><a href="">http://www.accellera.org/XMLSchema/IPXACT/1685-2014</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td><em>spirit-1685-2009-VE</em></td>
        <td>
        <a href="http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE">http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE</a> <br/> 
        <a href="http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/AMS-1.0">http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/AMS-1.0</a> <br/> 
        <a href="http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/CORE-1.0">http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/CORE-1.0</a> <br/> 
        <a href="http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/PDP-1.0">http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/PDP-1.0</a> <br/> 
        <a href="http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/POWER-1.0">http://www.accellera.org/XMLSchema/SPIRIT/1685-2009-VE/POWER-1.0</a>
        </td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">
            Depends: spirit-1685-2009 <br/>
            Depends: javax.xml.bind:jaxb-api
        </td>
    </tr>
    <tr>
        <td><em>spirit-1685-2009</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1685-2009">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1685-2009</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_5</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.5">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.5</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_4</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.4">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.4</a></td>
    </tr>
    <tr>
        <td colspan="2">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_2</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.2">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.2</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_1</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.1">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.1</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_0</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.0">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.0</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: javax.xml.bind:jaxb-api</td>
    </tr>
    <tr>
        <td colspan="2">&nbsp;</td>
    </tr>
    <tr>
        <td colspan="2">TGI.wsdl (Tight Generator Interface) processed by Apache Axis 1.4 for client stubs:</td>
    </tr>
    <tr>
        <td><em>spirit-1685-2009-wsdl-axis1</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1685-2009">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1685-2009</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: org.apache.axis:axis <br/> Depends: javax.xml.rpc:javax.xml.rpc-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_5-wsdl-axis1</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.5">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.5</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: org.apache.axis:axis <br/> Depends: javax.xml.rpc:javax.xml.rpc-api</td>
    </tr>
    <tr>
        <td><em>spirit-1_4-wsdl-axis1</em></td>
        <td><a href="http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.4">http://www.spiritconsortium.org/XMLSchema/SPIRIT/1.4</a></td>
    </tr>
    <tr>
        <td colspan="2" style="font-size: smaller">Depends: org.apache.axis:axis <br/> Depends: javax.xml.rpc:javax.xml.rpc-api</td>
    </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2">The exact JAXB version and package space depends on the build.</td>
        </tr>
    </tfoot>
</table>

The only intra project dependency exists between `spirit-1685-2009-VE` depending upon `spirit-1685-2009`.

All other subproject output artifacts are independent and freestanding of each other,
the only dependencies are listed with groupId:artifactId in the table above. 


Some attempt has been made to provide meta-data in the packaged JAR MANIFEST.MF to help consumers
identify environment expected at runtime environment.

A verbatim copy of the original XSD/WSDL schemas is provided in the packaged JARs in a package
'schema' nested below the generated class package.

A 'schema.properties' file is provided alongside XML descriptor documents help enumerate the
schema files.


### AXIS1

Why are we still using AXIS1 ?

This is due to the use of soapenc (http://schemas.xmlsoap.org/soap/encoding) standard
in the WSDL schema, so this limits the choice of SOAP stacks that can process the WSDL as-is.
Beware of the volume of CVEs (security vulnerability concerns) that exist today for Apache AXIS1 even in
the latest version 1.4 from 2006.

The AXIS1 impacted JARs are clearly named, separate and independent of the JAXB schema JARs.
It is not necessary to depend on any spirit-*-wsdl-axis1 project output JAR in order to use
the JAXB JAR, nor does any dependency exist in the reverse.

Potentially the online API is moving to REST in the future (information from Mar 2023).


### NOTES

JDK 11.0.17 has issue JDK-8193462 that affects building this project. of this due to Javadoc generated package-info.java
This concerns the use of package level annotations.
Upgrade to 11.0.18 or maybe downgrade to older versions should side-step this matter.



### LEGALS

This gradle project, code, configuration and documentation for which Darryl L. Miles is the owner
are licensed under the MIT license.

This project contains copyrighted works that are the owned by Accellera&trade; System Initiative.
This project contains components that are redistributed under the terms of the XMLSchema licensing
by Accellera&trade; System Initiative copies of the terms can be found:
 * online at http://www.accellerca.org/XMLSchema/ 
 * in the text at the top of the individual XSD, WSDL, XML and HTML <br/>
      files owned by Accellera&trade; System Initiative
 * in a LICENSE files located in this project around **/src/main/schema/LICENSE
 * in the output JARs containing verbatim schema files

This project is neither affiliated to nor endorsed by Accellera&trade; Systems Initiative

Trademarks and trade names are the property of their respective owners.


### Useful Links

 * [Top Level Page](https://dlmiles.github.io/java-schema-ipxact)
 * [Github-Pages Maven2 Artifact Browse](https://dlmiles.github.io/java-schema-ipxact/maven2)
 * [Github Package Browse](https://github.com/dlmiles/java-schema-ipxact/packages)
 * [JavaDoc](https://dlmiles.github.io/java-schema-ipxact/javadoc)
