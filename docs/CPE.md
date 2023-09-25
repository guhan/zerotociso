# Common Platform Enumeration (CPE)
A "CPE entry" typically refers to a Common Platform Enumeration entry, which is used to uniquely identify software and hardware products in a standardized way. 

- CPE entries follow a specific format defined by the Common Vulnerabilities and Exposures (CVE) project. 
- A CPE entry consists of several fields separated by colons (":")

```
cpe:/<part>:<vendor>:<product>:<version>:<update>:<edition>:<language>
```

- ```<part>```: This field specifies the type or part of the product. It can be one of the following values:
  - a: Application
  - o: Operating System
  - h: Hardware
- ```<vendor>```: This field identifies the vendor or manufacturer of the product.
- ```<product>```: This field specifies the product name.
- ```<version>```: This field indicates the version of the product. It can include version numbers or identifiers.
- ```<update>```: This field is used to specify an update or service pack for the product, if applicable.
- ```<edition>```: This field specifies the edition or variant of the product, if applicable.
- ```<language>```: This field indicates the language or localization of the product, if applicable.
