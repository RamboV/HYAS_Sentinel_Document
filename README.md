# HYAS Insight

![HYAS](https://www.hyas.com/hubfs/logo-1.svg "HYAS")
HYAS Insight provides On-Demand Enrichment of Passive DNS, Dynamic DNS, Passive Hash, SSL Certificate, Device Geo (Mobile Geolocation), Sinkhole, and Whois endpoints using the HYAS Insight enrichment API source.

<br>

 This connector is available in the following products and regions:

 | Service | Class | Regions |
 | ------ | ------ | ------ |
 | Logic Apps | Standard | All [Logic Apps regions](https://azure.microsoft.com/en-us/global-infrastructure/services/?products=logic-apps&regions=all) except the following:<br>-Azure Government regions<br>-Azure China regions |
 | Power Automate | Premium | All [Power Automate regions](https://docs.microsoft.com/en-us/power-automate/regions-overview) except the following:<br>-US Government (GCC)<br>-US Government (GCC High)<br>-China Cloud operated by 21Vianet |
 | Power Apps | Premium | All [Power Apps regions](https://docs.microsoft.com/en-us/power-platform/admin/regions-overview#what-regions-are-available) except the following:<br>-US Government (GCC)<br>-US Government (GCC High)<br>-China Cloud operated by 21Vianet |

<br>

## Pre-requisites
To use this integration, you need to have a HYAS Insight API Key provisioned by HYAS Infosec Inc to authenticate requests to HYAS Insight API.

<br>

## Creating a connection
To connect your account, you will need the following information:

| Name | Type | Description
 | ------ | ------ | ------ |
 | X-API-Key | securestring | The X-API-Key for HYAS Insight |
  
<br>

 ## Throttling Limits
 | Name | Calls | Renewal Period
 | ------ | ------ | ------ |
 | API calls per connection | 1000 | 1 Second |
 
<br>

  
 ## Actions:
 | Action Name | Description
  | ------ | ------ |
  | [Retrieve Passive DNS Information for Domain or IP Address](#retrieve-passive-dns-information-for-domain-or-ip-address) |  Retrieve on demand Passive DNS enrichment data for Domain or IP Address |
  | [Retrieve Whois Information for Domain or Email Address or Phone Number](#retrieve-whois-information-for-domain-or-email-address-or-phone-number) | Retrieve on demand Whois enrichment data for Domain or Email Address or PhoneNumber |
  | [Retrieve Dynamic DNS Information for IP Address or Email Address](#retrieve-dynamic-dns-information-for-ip-address-or-email-address) | Retrieve on demand Dynamic DNS enrichment data for IP Address or Email Address |
  | [Retrieve Passive Hash Information for IP Address](#retrieve-passive-hash-information-for-ip-address) |Retrieve on demand Passive Hash enrichment data for IP Address |
| [Retrieve Sinkhole Information for IP Address](#retrieve-sinkhole-information-for-ip-address) | Retrieve on demand Sinkhole enrichment data for IP Address |
  | [Retrieve Device Geo Information for IP Address](#retrieve-device-geo-information-for-ip-address) | Retrieve on demand Device Geo enrichment data for IP Address |
 | [Retrieve SSL Certificate Information for IP Address](#retrieve-ssl-certificate-information-for-ip-address) | Retrieve on demand SSL Certificate enrichment data for IP Address |

<br>

### Retrieve Passive DNS Information for Domain or IP Address

Operation ID: PASSIVE_DNS

Retrieve on demand Passive DNS enrichment data for Domain or IP Address

#### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain |  | string | Domain you want to enrich |
 | IP Address | ipv4 |  | string | IPv4 Address you want to enrich |

**Note: Any one of the parameters is required.**

#### Returns
##### **Body** : [PassiveDNSResults](#passivednsresults)

<br>


### Retrieve Whois Information for Domain or Email Address or Phone Number

Operation ID: WHOIS

Retrieve on demand Whois enrichment data for Domain or Email Address or Phone Number

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain |  | string | Domain you want to enrich. If Current is set to true, API will retrieve Whois Current Information, if it set to false (defalut), API will retrieve Whois Historic Information |
 | Email Address | email |  | string | Email Address you want to enrich |
 | Phone Number | phone |  | string | Phone Number you want to enrich ( e164 format. Eg: ( +41585855634 ) ) |

**Note: Any one of the parameters is required.**

 #### Returns
##### **Body** : <br>[WhoisResult](#whoishistoricresult)<br> If Current is set to true: [WhoisResult](#whoiscurrentresult)


<br>

### Retrieve Dynamic DNS Information for IP Address or Email Address

Operation ID: DYNAMIC_DNS

Retrieve on demand Dynamic DNS enrichment data for IP Address or Email Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 |  | string | IPv4 Address you want to enrich |
 | Email Address | email |  | string |Email Address you want to enrich |
 
**Note: Any one of the parameters is required.**

  #### Returns
##### **Body** :  [DynamicDNSResult](#dynamicdnsresult)

<br>

### Retrieve Passive Hash Information for IP Address 

Operation ID: PASSIVE_HASH

Retrieve on demand Passive Hash enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | string | IPv4 Address you want to enrich |


 #### Returns
##### **Body** : [passiveHashResult](#passivehashresult)

<br>

 ### Retrieve Sinkhole Information for IP Address

Operation ID: SINKHOLE

Retrieve on demand Sinkhole enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | string | IPv4 Address you want to enrich |

 #### Returns
##### **Body** :  [SinkholeResult](#sinkholeresult)

<br>

### Retrieve Device Geo Information for IP Address

Operation ID: DEVICE_GEO

Retrieve on demand Device Geo enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 Address | ipv4 |  | string | IPv4 Address you want to enrich |
 | IPv6 Address | ipv6 |  | string | IPv6 Address you want to enrich |
 
**Note: Any one of the parameters is required.**

 #### Returns
##### **Body** :  [DeviceGeoResult](#devicegeoresult)

<br>

### Retrieve SSL Certificate Information for IP Address

 Operation ID: SSL_CERTIFICATE

Retrieve on demand SSL Certificate enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | string | IPv4 Address you want to enrich |
 
 #### Returns
##### **Body** : [SSLCertificateResult](#sslcertificateresult)

<br>


### PassiveDNSResults

| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
| cert_name | cert_name | string | The certificate provider name |
|count | count | number | The passive dns count |
|domain| domain | string | The domain of the passive dns information requested |
|first_seen | first_seen | string | The first time this domain was seen | 
|city_name | ip.geo.city_name | string | City of the ip organization |
|country_iso_code | ip.geo.country_iso_code | string | Country ISO code of the ip organization |
|country_name | ip.geo.country_name | string | Country name of the ip organization |
|location_latitude | ip.geo.location_latitude | string | The latitude of the ip organization |
|location_longitude | ip.geo.location_longitude | string | The longitude of the ip organization |
|postal_code | ip.geo.postal_code | string | The postal code of the ip organization |
|ip | ip.ip | string | IP of the organization |
|autonomous_system_number | ip.isp.autonomous_system_number | string | The ASN of the ip |
|autonomous_system_organization | ip.isp.autonomous_system_organization | string | The ASO of the ip |
|ip_address | ip.isp.ip_address | string | The IP |
|isp | ip.isp.isp | string | The Internet Service Provider |
|organization | ip.isp.organization | string | The ISP organization |
|ipv4 | ipv4 | string | The ipv4 address of the passive dns record |
|ipv6 | ipv6 | string | The ipv6 address of the passive dns record |
|last_seen | last_seen | string | The last time this domain was seen |
|sha1 | sha1 | string | The sha1 Information |
|sources | sources | string array | A list of pDNS providers which the data came from |

<br>


### WhoIsHistoricResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|address | address | string array | The address information |
|city | city | string array |  The city information |
|country | country | string array | The country information |
|data | data | string | The data information |
|datetime | datetime | string | The datetime information |
|domain | domain | string |  The domain of the registrant |
|domain_2tld | domain_2tld | string | The second-level domain of the registrant |
|domain_created_datetime | domain_created_datetime | string | The date and time when the Whois record was created |
|domain_expires_datetime | domain_expires_datetime | string | The date and time when the Whois record expires |
|domain_updated_datetime | domain_updated_datetime | string | The date and time when the Whois record was last updated |
|email | email | string array | The email information |
|idn_name | idn_name | string | The international domain name |
|meta_data | meta_data | string | The metadata information |
|name | name | string array | The contact name (registrant contact, administrative contact, technical contact, or abuse contact) |
|nameserver | nameserver | string array |  The nameserver domain |
|phone | phone.phone | string |  The phone number of the registrant in e164 format |
|carrier | phone.phone_info.carrier | string | Phone number carrier |
|country | phone.phone_info.country | string | Phone number country |
|geo | phone.phone_info.geo | string | Phone number geo. Can be city, province, region or country |
|privacy_punch | privacy_punch | boolean | True if this record has additional information bypassing privacy protect |
|registrar | registrar | string |  The domain registrar |
|whois_hash | whois_hash | string | Internal use |
|whois_id | whois_id | string | Internal use |

<br>

### WhoIsCurrentResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
| abuse_emails | items.abuse_emails | string array | The abuse emails information | 
| address | items.address | string array | The address information |
| city | items.city | string array | The city of the registrant |
| country  | items.country  | string array | The country of the registrant |
| data | items.data | string | The data information |
| datetime | items.datetime | string | The datetime information |
| domain | items.domain | string | The domain of the registrant |
| domain_2tld | items.domain_2tld | string | The second-level domain of the registrant |
| domain_created_datetime | items.domain_created_datetime | string | The date and time when the Whois record was created |
| domain_expires_datetime | items.domain_expires_datetime | string | The date and time when the Whois record expires |
| domain_updated_datetime | items.domain_updated_datetime | string | The date and time when the Whois record was last updated |
| email | items.email | string array |The email information |
| idn_name | items.idn_name | string | The international domain name |
| meta_data | items.meta_data | string | The metadata information |
| name | items.name | string array | The contact name (registrant contact, administrative contact, technical contact, or abuse contact) |
| nameserver | items.nameserver | string array | The nameserver domain |
| organization | items.organization | string array | The organization information |
| phone | items.phone | string array | The phone number of the registrant in e164 format |
| registrar | items.registrar  | string | The domain registrar 
| state | items.state | string array | The state where domain was registered |
| whois_hash | items.whois_hash | string | The hash information |
| whois_id | items.whois_id | string | The whois id information |
| domain | items.whois_nameserver.domain | string | The nameserver’s domain information |
| domain_2tld | items.whois_nameserver.domain_2tld | string | The nameserver’s domain_2tld information |
| whois_related_nameserver_id | items.whois_nameserver.whois_related_nameserver_id | string | The nameserver’s Id Information |
| address | items.whois_pii.address | string | The personal identity address information |
| city | items.whois_pii.city | string | The personal identity city information |
| data | items.whois_pii.data | string | The personal identity data information |
| email | items.whois_pii.email | string | The personal identity email information |
| geo_country_alpha_2 | items.whois_pii.geo_country_alpha_2 | String | The personal identity country information |
| name | items.whois_pii.name | string | The personal identity name information |
| organization | items.whois_pii.organization| string | The personal identity organization information |
| phone_e164 | items.whois_pii.phone_e164 | string | The personal identity Phone_e164 information |
| state | items.whois_pii.state | string | The personal identity state information |
| whois_related_pii_id | items.whois_pii.whois_related_pii_id | string | The personal identity Id information |
| whois_related_type | items.whois_pii.whois_related_type | string | The personal identity related information |
| source | source | string | The source information |
| total_count | total_count | number | The total count information |

<br>

### DynamicDNSResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|a_record | a_record | string | The A record for the domain |
|account | account | string | The account holder name |
|created | created | string |The date which the domain was created |
|created_ip | created_ip | string | The ip address of the account holder |
|domain | domain | string |The domain associated with the dynamic dns information |
|domain_creator_ip | domain_creator_ip | string | The ip address of the domain creator |
|email | email | string | The email address connected to the domain | The email address connected to the domain |

<br>


### PassiveHashResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|domain | domain | string | The domain of the passive hash information requested |
|md5_count | md5_count | number | The passive dns count |

<br>


### SinkholeResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|count | count | string | The sinkhole count |
|country_name | country_name | string | The country of the ip |
|data_port | data_port | number | The data port |
|datetime | datetime | string | The first seen date of the sinkhole |
|ipv4 | ipv4 | string |  The ipv4 of the sinkhole |
|last_seen | last_seen | string | The last seen date of the sinkhole |
|organization_name | organization_name | string | The isp organization for the ip |
|sink_source | sink_source | string | The ipv4 of the sink source |

<br>


### DeviceGeoResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|datetime | datetime | string | A date-time string in RFC 3339 format |
|device_geo_id | device_geo_id | number | Internal record ID |
|device_user_agent | device_user_agent | string | The user agent for the device |
|geo_country_alpha_2 | geo_country_alpha_2 | string | The ISO 3316 alpha-2 code for the country associated with the latitude/longitude reported |
|geo_horizontal_accuracy | geo_horizontal_accuracy | string | The GPS horizontal accuracy |
|ipv4 | ipv4 | string | The ipv4 address assigned to the device. A device may have either or ipv4 and ipv6 |
|ipv6 | ipv6 | string | The ipv6 address assigned to the device. A device may have either or ipv4 and ipv6 |
|latitude | latitude | number | Units are degrees on the WGS 84 spheroid |
|longitude | longitude | number | Units are degrees on the WGS 84 spheroid |
|wifi_bssid | wifi_bssid | string | The BSSID (MAC address) of the WIFI router that the device communicated through |
|wifi_ssid | wifi_ssid | string | The SSID (name) of the WIFI network that the device communicated through |

<br>


### SSLCertificateResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|related_count | related_count | number | The number of ip addresses connected to this certificate |
|ip | ssl_certs.ip | string | The ip address associated with certificate |
|cert_key | ssl_certs.ssl_cert.cert_key | string | The certificate key (sha1) |
|expire_date | ssl_certs.ssl_cert.expire_date | string |The expiry date of the certificate |
|issue_date | ssl_certs.ssl_cert.issue_date | string | The issue date of the certificate |
|issuer_commonName | ssl_certs.ssl_cert.issuer_commonName | string | The common name that the certificate was issued from |
|issuer_countryName | ssl_certs.ssl_cert.issuer_countryName | string | The country ISO the certificate was issued from |
|issuer_localityName | ssl_certs.ssl_cert.issuer_localityName | string | The city where the issuer company is legally located |
|issuer_organizationName | ssl_certs.ssl_cert.issuer_organizationName | string |  The organization name that issued the certificate |
|issuer_organizationalUnitName| ssl_certs.ssl_cert.issuer_organizationalUnitName | string | The organization unit name that issued the certificate |
|issuer_stateOrProvinceName | ssl_certs.ssl_cert.issuer_stateOrProvinceName | string | The issuer state or province |
|md5 | ssl_certs.ssl_cert.md5 | string | The certificate MD5 |
|serial_number | ssl_certs.ssl_cert.serial_number |  number | The certificate serial number |
|sha1 | ssl_certs.ssl_cert.sha1 | string | The certificate sha1 |
|sha_256 | ssl_certs.ssl_cert.sha_256 | string | The certificate sha256 |
|sig_algo | ssl_certs.ssl_cert.sig_algo | string | The certificate signature algorithm |
|signature | ssl_certs.ssl_cert.signature | string array | Signature split into multiple lines |
|ssl_version | ssl_certs.ssl_cert.ssl_version | number | The SSL version |
|subject_commonName | ssl_certs.ssl_cert.subject_commonName | string | The subject name that the certificate was issued to |
|subject_countryName | ssl_certs.ssl_cert.subject_countryName | string | The country the certificate was issued to |
|subject_localityName | ssl_certs.ssl_cert.subject_localityName | string |  The city where the subject company is legally located |
|subject_organizationName | ssl_certs.ssl_cert.subject_organizationName |  string | The organization name that received the certificate
|subject_organizationalUnitName | ssl_certs.ssl_cert.subject_organizationalUnitName |  string | The organization unit name that recieved the certificate |
|subject_stateOrProvinceName | ssl_certs.ssl_cert.subject_stateOrProvinceName | string | The state or province name where the subject company is located |
|timestamp | ssl_certs.ssl_cert.timestamp |  string | The certificate date and time |
