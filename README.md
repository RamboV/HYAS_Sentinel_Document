# HYAS Insight

![HYAS](https://www.hyas.com/hubfs/logo-1.svg "HYAS")
HYAS Insight integration to Microsoft Azure Sentinel provides direct, high volume access to HYAS Insight data. It enables investigators and analysts to understand and defend against cyber adversaries and their infrastructure.

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
 | X-API-Key | securestring | The X-API-Key for HYAS Insight. |
  
<br>

 ## Throttling Limits
 | Name | Calls | Renewal Period
 | ------ | ------ | ------ |
 | API calls per connection | 1000 | 1 Second |
 
<br>

  
 ## Actions:
 | Action Name | Description
  | ------ | ------ |
  | [Retrieve Passive DNS information for domain](#retrieve-passive-dns-information-for-domain) |  Retrieve Passive DNS enrichment data for domain. |
  | [Retrieve Passive DNS information for IP address](#retrieve-passive-dns-information-for-ip-address) |  Retrieve Passive DNS enrichment data for IP address. |
  | [Retrieve Historic WHOIS information for domain](#retrieve-historic-whois-information-for-domain) | Retrieve Historic WHOIS enrichment data for domain. |
  | [Retrieve Historic WHOIS information for email address](#retrieve-historic-whois-information-for-email-address) | Retrieve Historic WHOIS enrichment data for email address. |
  | [Retrieve Historic WHOIS information for phone number](#retrieve-historic-whois-information-for-phone-number) | Retrieve Historic WHOIS enrichment data for phone number. |
  | [Retrieve Current WHOIS information for domain](#retrieve-current-whois-information-for-domain) | Retrieve Current WHOIS enrichment data for domain. |
  | [Retrieve Dynamic DNS information for IP address](#retrieve-dynamic-dns-information-for-ip-address) | Retrieve Dynamic DNS enrichment data for IP address. |
  | [Retrieve Dynamic DNS information for email address](#retrieve-dynamic-dns-information-for-email-address) | Retrieve Dynamic DNS enrichment data for email address. |
  | [Retrieve Passive Hash information for IP address](#retrieve-passive-hash-information-for-ip-address) |Retrieve Passive Hash enrichment data for IP address. |
  | [Retrieve Sinkhole information for IP address](#retrieve-sinkhole-information-for-ip-address) | Retrieve Sinkhole enrichment data for IP address. |
  | [Retrieve SSL certificate information for IP address](#retrieve-ssl-certificate-information-for-ip-address) | Retrieve SSL certificate enrichment data for IP address. |
  | [Retrieve Device Geo information for IPv4 address](#retrieve-device-geo-information-for-ipv4-address) | Retrieve Device Geo enrichment data for IPv4 address. |
  | [Retrieve Device Geo information for IPv6 address](#retrieve-device-geo-information-for-ipv6-address) | Retrieve Device Geo enrichment data for IPv6 address. |
  

<br>

### Retrieve Passive DNS information for domain

Operation ID: DOMAIN_PASSIVE_DNS

Retrieve Passive DNS enrichment data for domain.

#### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain | True  | string | Domain you want to enrich. |


#### Returns
##### **Body** : [Passive_DNS_Results](#passive_dns_results)

<br>

### Retrieve Passive DNS information for IP address

Operation ID: IP_PASSIVE_DNS

Retrieve Passive DNS enrichment data for IP address.

#### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 address | ipv4 |  True | string | IPv4 address you want to enrich. |


#### Returns
##### **Body** : [Passive_DNS_Results](#passive_dns_results)

<br>

### Retrieve Historic WHOIS information for domain

Operation ID: DOMAIN_WHOIS_HISTORIC

Retrieve Historic WHOIS enrichment data for domain.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain | True | string | Domain you want to enrich. |

 #### Returns
##### **Body** : [Historic_WHOIS_Results](#historic_whois_results)

<br>

### Retrieve Historic WHOIS information for email address

Operation ID: EMAIL_WHOIS_HISTORIC

Retrieve Historic WHOIS enrichment data for email address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Email address | email | True  | string | Email address you want to enrich. |

 #### Returns
##### **Body** : [Historic_WHOIS_Results](#historic_whois_results)

<br>

### Retrieve Historic WHOIS information for phone number

Operation ID: PHONE_WHOIS_HISTORIC

Retrieve Historic WHOIS enrichment data for phone number.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Phone number | phone | True  | string | Phone number you want to enrich.( e164 format. Eg: ( +41585855634 ) ) |

 #### Returns
##### **Body** : [Historic_WHOIS_Results](#historic_whois_results)

<br>

### Retrieve Current WHOIS information for domain

Operation ID: DOMAIN_WHOIS_CURRENT

Retrieve Current WHOIS enrichment data for domain.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain | True | string | Domain you want to enrich. |


 #### Returns
##### **Body** : [Current_WHOIS_Results](#current_whois_results)


<br>

### Retrieve Dynamic DNS information for IP address

Operation ID: IP_DYNAMIC_DNS

Retrieve Dynamic DNS enrichment data for IP address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 address | ip | True | string | IPv4 address you want to enrich. |


  #### Returns
##### **Body** :  [Dynamic_DNS_Results](#dynamic_dns_results)

<br>

### Retrieve Dynamic DNS information for email address

Operation ID: DYNAMIC_DNS

Retrieve Dynamic DNS enrichment data for email address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Email address | email | True | string |Email address you want to enrich. |
 
  #### Returns
##### **Body** :  [Dynamic_DNS_Results](#dynamic_dns_results)


<br>

### Retrieve Passive Hash information for IP address 

Operation ID: PASSIVE_HASH

Retrieve Passive Hash enrichment data for IP address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 address | ipv4 | True | string | IPv4 address you want to enrich. |


 #### Returns
##### **Body** : [passive_Hash_Results](#passive_hash_results)

<br>

 ### Retrieve Sinkhole information for IP address

Operation ID: SINKHOLE

Retrieve Sinkhole enrichment data for IP address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 address | ipv4 | True | string | IPv4 address you want to enrich. |

 #### Returns
##### **Body** :  [Sinkhole_Results](#sinkhole_results)

<br>

### Retrieve Device Geo information for IPv4 address

Operation ID: IPV4_DEVICE_GEO

Retrieve Device Geo enrichment data for IPv4 address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 address | ipv4 | True | string | IPv4 address you want to enrich. |

 #### Returns
##### **Body** :  [Device_Geo_Results](#device_geo_results)

<br>

### Retrieve Device Geo information for IPv6 address

Operation ID: IPV6_DEVICE_GEO

Retrieve Device Geo enrichment data for IPv6 address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv6 address | ipv6 | True | string | IPv6 address you want to enrich. |
 

 #### Returns
##### **Body** :  [Device_Geo_Results](#device_geo_results)

<br>


### Retrieve SSL certificate information for IP address

 Operation ID: SSL_CERTIFICATE

Retrieve SSL certificate enrichment data for IP address.

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 address | ip | True | string | IPv4 address you want to enrich. |
 
 #### Returns
##### **Body** : [SSL_Certificate_Results](#ssl_certificate_results)

<br>


### Passive_DNS_Results

| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
| cert_name | cert_name | string | The certificate provider name. |
|count | count | number | The passive dns count. |
|domain| domain | string | The domain of the passive dns information requested. |
|first_seen | first_seen | string | The first time this domain was seen. | 
|city_name | ip.geo.city_name | string | City of the ip organization. |
|country_iso_code | ip.geo.country_iso_code | string | Country ISO code of the ip organization. |
|country_name | ip.geo.country_name | string | Country name of the ip organization. |
|location_latitude | ip.geo.location_latitude | string | The latitude of the ip organization. |
|location_longitude | ip.geo.location_longitude | string | The longitude of the ip organization. |
|postal_code | ip.geo.postal_code | string | The postal code of the ip organization. |
|ip | ip.ip | string | IP of the organization. |
|autonomous_system_number | ip.isp.autonomous_system_number | string | The ASN of the ip. |
|autonomous_system_organization | ip.isp.autonomous_system_organization | string | The ASO of the ip. |
|ip_address | ip.isp.ip_address | string | The IP. |
|isp | ip.isp.isp | string | The Internet Service Provider. |
|organization | ip.isp.organization | string | The ISP organization. |
|ipv4 | ipv4 | string | The ipv4 address of the passive dns record. |
|ipv6 | ipv6 | string | The ipv6 address of the passive dns record. |
|last_seen | last_seen | string | The last time this domain was seen. |
|sha1 | sha1 | string | The sha1 information. |
|sources | sources | string array | A list of pDNS providers which the data came from. |

<br>


### Historic_WHOIS_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|address | address | string array | The address information. |
|city | city | string array |  The city information. |
|country | country | string array | The country information. |
|data | data | string | The data information. |
|datetime | datetime | string | The datetime information. |
|domain | domain | string |  The domain of the registrant. |
|domain_2tld | domain_2tld | string | The second-level domain of the registrant. |
|domain_created_datetime | domain_created_datetime | string | The date and time when the Whois record was created. |
|domain_expires_datetime | domain_expires_datetime | string | The date and time when the Whois record expires. |
|domain_updated_datetime | domain_updated_datetime | string | The date and time when the Whois record was last updated. |
|email | email | string array | The email information. |
|idn_name | idn_name | string | The international domain name. |
|meta_data | meta_data | string | The metadata information. |
|name | name | string array | The name information. |
|nameserver | nameserver | string array |  The nameserver information. |
|phone | phone.phone | string |  The phone number of the registrant in e164 format. |
|carrier | phone.phone_info.carrier | string | Phone number carrier. |
|country | phone.phone_info.country | string | Phone number country. |
|geo | phone.phone_info.geo | string | Phone number geo can be city or province or region or country. |
|privacy_punch | privacy_punch | boolean | True if this record has additional information bypassing privacy protect. |
|registrar | registrar | string |  The domain registrar. |
|whois_hash | whois_hash | string | The hash information. |
|whois_id | whois_id | string | The whois id information. |

<br>

### Current_WHOIS_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
| abuse_emails | items.abuse_emails | string array | The abuse emails information. | 
| address | items.address | string array | The address information. |
| city | items.city | string array | The city of the registrant. |
| country  | items.country  | string array | The country of the registrant. |
| data | items.data | string | The data information. |
| datetime | items.datetime | string | The datetime information. |
| domain | items.domain | string | The domain of the registrant. |
| domain_2tld | items.domain_2tld | string | The second-level domain of the registrant. |
| domain_created_datetime | items.domain_created_datetime | string | The date and time when the Whois record was created. |
| domain_expires_datetime | items.domain_expires_datetime | string | The date and time when the Whois record expires. |
| domain_updated_datetime | items.domain_updated_datetime | string | The date and time when the Whois record was last updated. |
| email | items.email | string array |The email information. |
| idn_name | items.idn_name | string | The international domain name. |
| meta_data | items.meta_data | string | The metadata information. |
| name | items.name | string array | The contact name (registrant contact, administrative contact, technical contact, or abuse contact). |
| nameserver | items.nameserver | string array | The nameserver domain. |
| organization | items.organization | string array | The organization information. |
| phone | items.phone | string array | The phone number of the registrant in e164 format. |
| registrar | items.registrar  | string | The domain registrar. | 
| state | items.state | string array | The state where domain was registered. |
| whois_hash | items.whois_hash | string | The hash information. |
| whois_id | items.whois_id | string | The whois id information. |
| domain | items.whois_nameserver.domain | string | The nameserver’s domain information. |
| domain_2tld | items.whois_nameserver.domain_2tld | string | The nameserver’s domain_2tld information. |
| whois_related_nameserver_id | items.whois_nameserver.whois_related_nameserver_id | string | The nameserver’s Id Information. |
| address | items.whois_pii.address | string | The personal identity address information. |
| city | items.whois_pii.city | string | The personal identity city information. |
| data | items.whois_pii.data | string | The personal identity data information. |
| email | items.whois_pii.email | string | The personal identity email information. |
| geo_country_alpha_2 | items.whois_pii.geo_country_alpha_2 | String | The personal identity country information. |
| name | items.whois_pii.name | string | The personal identity name information. |
| organization | items.whois_pii.organization| string | The personal identity organization information. |
| phone_e164 | items.whois_pii.phone_e164 | string | The personal identity Phone_e164 information. |
| state | items.whois_pii.state | string | The personal identity state information. |
| whois_related_pii_id | items.whois_pii.whois_related_pii_id | string | The personal identity Id information. |
| whois_related_type | items.whois_pii.whois_related_type | string | The personal identity related information. |
| source | source | string | The source information. |
| total_count | total_count | number | The total count information. |

<br>

### Dynamic_DNS_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|a_record | a_record | string | The A record for the domain. |
|account | account | string | The account holder name. |
|created | created | string |The date which the domain was created. |
|created_ip | created_ip | string | The ip address of the account holder. |
|domain | domain | string |The domain associated with the dynamic dns information. |
|domain_creator_ip | domain_creator_ip | string | The ip address of the domain creator. |
|email | email | string | The email address connected to the domain. |

<br>


### Passive_Hash_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|domain | domain | string | The domain of the passive hash information requested. |
|md5_count | md5_count | number | The passive dns count. |

<br>


### Sinkhole_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|count | count | string | The sinkhole count. |
|country_name | country_name | string | The country of the ip. |
|data_port | data_port | number | The data port. |
|datetime | datetime | string | The first seen date of the sinkhole. |
|ipv4 | ipv4 | string |  The ipv4 of the sinkhole. |
|last_seen | last_seen | string | The last seen date of the sinkhole. |
|organization_name | organization_name | string | The isp organization for the ip. |
|sink_source | sink_source | string | The ipv4 of the sink source. |

<br>


### Device_Geo_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|datetime | datetime | string | A date-time string in RFC 3339 format. |
|device_geo_id | device_geo_id | string | Internal record ID. |
|device_user_agent | device_user_agent | string | The user agent for the device. |
|geo_country_alpha_2 | geo_country_alpha_2 | string | The ISO 3316 alpha-2 code for the country associated with the latitude/longitude reported. |
|geo_horizontal_accuracy | geo_horizontal_accuracy | number | The GPS horizontal accuracy. |
|ipv4 | ipv4 | string | The ipv4 address assigned to the device. A device may have either or ipv4 and ipv6. |
|ipv6 | ipv6 | string | The ipv6 address assigned to the device. A device may have either or ipv4 and ipv6. |
|latitude | latitude | number | Units are degrees on the WGS 84 spheroid. |
|longitude | longitude | number | Units are degrees on the WGS 84 spheroid. |
|wifi_bssid | wifi_bssid | string | The BSSID (MAC address) of the WIFI router that the device communicated through. |
|wifi_ssid | wifi_ssid | string | The SSID (name) of the WIFI network that the device communicated through. |

<br>


### SSL_Certificate_Results
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|related_count | related_count | number | The number of ip addresses connected to this certificate. |
|ip | ssl_certs.ip | string | The ip address associated with certificate. |
|cert_key | ssl_certs.ssl_cert.cert_key | string | The certificate key (sha1). |
|expire_date | ssl_certs.ssl_cert.expire_date | string |The expiry date of the certificate. |
|issue_date | ssl_certs.ssl_cert.issue_date | string | The issue date of the certificate. |
|issuer_commonName | ssl_certs.ssl_cert.issuer_commonName | string | The common name that the certificate was issued from. |
|issuer_countryName | ssl_certs.ssl_cert.issuer_countryName | string | The country ISO the certificate was issued from. |
|issuer_localityName | ssl_certs.ssl_cert.issuer_localityName | string | The city where the issuer company is legally located. |
|issuer_organizationName | ssl_certs.ssl_cert.issuer_organizationName | string |  The organization name that issued the certificate. |
|issuer_organizationalUnitName| ssl_certs.ssl_cert.issuer_organizationalUnitName | string | The organization unit name that issued the certificate. |
|issuer_stateOrProvinceName | ssl_certs.ssl_cert.issuer_stateOrProvinceName | string | The issuer state or province. |
|md5 | ssl_certs.ssl_cert.md5 | string | The certificate MD5. |
|serial_number | ssl_certs.ssl_cert.serial_number |  number | The certificate serial number. |
|sha1 | ssl_certs.ssl_cert.sha1 | string | The certificate sha1. |
|sha_256 | ssl_certs.ssl_cert.sha_256 | string | The certificate sha256. |
|sig_algo | ssl_certs.ssl_cert.sig_algo | string | The certificate signature algorithm. |
|signature | ssl_certs.ssl_cert.signature | string array | Signature split into multiple lines. |
|ssl_version | ssl_certs.ssl_cert.ssl_version | number | The SSL version. |
|subject_commonName | ssl_certs.ssl_cert.subject_commonName | string | The subject name that the certificate was issued to. |
|subject_countryName | ssl_certs.ssl_cert.subject_countryName | string | The country the certificate was issued to. |
|subject_localityName | ssl_certs.ssl_cert.subject_localityName | string |  The city where the subject company is legally located. |
|subject_organizationName | ssl_certs.ssl_cert.subject_organizationName |  string | The organization name that received the certificate. |
|subject_organizationalUnitName | ssl_certs.ssl_cert.subject_organizationalUnitName |  string | The organization unit name that recieved the certificate. |
|subject_stateOrProvinceName | ssl_certs.ssl_cert.subject_stateOrProvinceName | string | The state or province name where the subject company is located. |
|timestamp | ssl_certs.ssl_cert.timestamp |  string | The certificate date and time. |
