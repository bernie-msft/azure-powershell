﻿<!--
    Please leave this section at the top of the change log.

    Changes for the current release should go under the section titled "Current Release", and should adhere to the following format:

    ## Current Release
    * Overview of change #1
        - Additional information about change #1
    * Overview of change #2
        - Additional information about change #2
        - Additional information about change #2
    * Overview of change #3
    * Overview of change #4
        - Additional information about change #4

    ## YYYY.MM.DD - Version X.Y.Z (Previous Release)
    * Overview of change #1
        - Additional information about change #1
-->
## Current Release

## Version 4.4.1

## Version 4.4.0
* Added support for endpoint services to Virtual Network Subnets
    - Updated Add-AzureRmVirtualSubnetConfig: Added optional parameter -ServiceEndpoint
    - Updated New-AzureRmVirtualSubnetConfig: Added optional parameter -ServiceEndpoint
    - Updated Set-AzureRmVirtualSubnetConfig: Added optional parameter -ServiceEndpoint
* Added cmdlet to list endpoint services available in the location
    - Get-AzureRmVirtualNetworkAvailableEndpointService
* Added the ability to configure external radius based P2S authentication to the following commandlets
    - New-AzureVirtualNetworkGateway
    - Set-AzureVirtualNetworkGateway
    - Set-AzureRmVirtualNetworkGatewayVpnClientConfig
* Added cmdlet to allow generation of VpnProfiles for external radius based P2S
    - New-AzureRmVpnClientConfiguration
	  - Get-AzureRmVpnClientConfiguration
* Added support for SKU parameter to Public IP Addresses and Load Balancers
    - Updated New-AzureRMLoadBalancer: Added optional parameter -Sku
    - Updated New-AzureRMPublicIpAddress: Added optional parameter -Sku
* Added support for DisableOutboundSNAT to Load Balancer Rules
    - Updated New-AzureRMLoadBalancerRuleConfig: Added optional parameter DisableOutboundSNAT
    - Updated Add-AzureRMLoadBalancerRuleConfig: Added optional parameter DisableOutboundSNAT
    - Updated Set-AzureRMLoadBalancerRuleConfig: Added optional parameter DisableOutboundSNAT
* Added support for IkeV2 P2S
    - Updated New-AzureRmVirtualNetworkGateway: Added optional parameter -VpnClientProtocol, defaults to [ "SSTP", "IkeV2" ]
    - Updated Set-AzureRmVirtualNetworkGateway: Added optional parameter -VpnClientProtocol
* Added new commands for VpnDeviceConfiguration Scripts
    - Get-AzureRmVirtualNetworkGatewaySupportedVpnDevices
    - Get-AzureRmVirtualNetworkGatewayConnectionVpnDeviceConfigScript
* Added support for MultiValued rules in Network Security Rules and Effective Network Security Rules
    - Updated Add-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameters to accept a list of strings
    - Updated New-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix  parameter to accept a list of strings
    - Updated Set-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameter to accept a list of strings
    - Updated Add-AzureRmNetworkSecurityRuleConfig: Updated SourcePortRange, DestinationPortRange, SourceAddressPrefix parameter to accept a list of strings
    - Updated New-AzureRmNetworkSecurityGroup : Updated SecurityRules parameter to accept SourcePortRange, DestinationPortRange, SourceAddressPrefix parameters which are list of strings in PSSecurityRule object
    - Updated Get-AzureRmEffectiveNetworkSecurityGroup: Added parameter TagMap
    - Updated Get-AzureRmEffectiveNetworkSecurityGroup: Updated returned PSEffectiveSecurityRule object with SourcePortRange, DestinationPortRange, SourceAddressPrefix parameters which are list of strings.
* Added support for DDoS protection for virtual networks
    - Updated New-AzureRmVirtualNetwork: Added switch parameters EnableDDoSProtection and EnableVmProtection
    - Added properties EnableDDoSProtection and EnableVmProtection in PSVirtualNetwork object
* Added support for Highly Available Internal Load Balancer
    - Updated Add-AzureRmLoadBalancerRuleConfig: Added All as an acceptable value for Protocol parameter
    - Updated New-AzureRmLoadBalancerRuleConfig: Added All as an acceptable value for Protocol parameter
    - Updated Set-AzureRmLoadBalancerRuleConfig: Added All as an acceptable value for Protocol parameter
* Added support for Application Security Groups
    - Added New-AzureRmApplicationSecurityGroup
    - Added Get-AzureRmApplicationSecurityGroup
    - Added Remove-AzureRmApplicationSecurityGroup
    - Updated New-AzureRmNetworkInterface: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated New-AzureRmNetworkInterfaceIpConfig: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated Add-AzureRmNetworkInterfaceIpConfig: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated Set-AzureRmNetworkInterfaceIpConfig: Added optional parameters ApplicationSecurityGroup and ApplicationSecurityGroupId
    - Updated New-AzureRmNetworkSecurityRuleConfig: Added optional parameters SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, and DestinationApplicationSecurityGroupId
    - Updated Add-AzureRmNetworkSecurityRuleConfig: Added optional parameters SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, and DestinationApplicationSecurityGroupId
    - Updated Set-AzureRmNetworkSecurityRuleConfig: Added optional parameters SourceApplicationSecurityGroup, SourceApplicationSecurityGroupId, DestinationApplicationSecurityGroup, and DestinationApplicationSecurityGroupId
	
## Version 4.3.1

## Version 4.3.0
* New-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. New optional parameter added
	- PeerAddressType
* Set-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. New optional parameter added
	- PeerAddressType
* Remove-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. New optional parameter added
	- PeerAddressType
* Marked parameter -ProbeEnabled as obsolete
    - Add-AzureRmApplicationGatewayBackendHttpSettings
    - New-AzureRmApplicationGatewayBackendHttpSettings
    - Set-AzureRmApplicationGatewayBackendHttpSettings 

## Version 4.2.1

## Version 4.2.0
* New-AzureRmIpsecPolicy: SALifeTimeSeconds and SADataSizeKilobytes are no longer mandatory parameters
    - SALifeTimeSeconds defaults to 27000 seconds
    - SADataSizeKilobytes defaults to 102400000 KB
* Added support for custom cipher suite configuration using ssl policy and listing all ssl options api in Application Gateway
    - Added optional parameter -PolicyType, -PolicyName, -MinProtocolVersion, -Ciphersuite
        - Add-AzureRmApplicationGatewaySslPolicy
        - New-AzureRmApplicationGatewaySslPolicy
        - Set-AzureRmApplicationGatewaySslPolicy
    - Added Get-AzureRmApplicationGatewayAvailableSslOptions (Alias: List-AzureRmApplicationGatewayAvailableSslOptions)
    - Added Get-AzureRmApplicationGatewaySslPredefinedPolicy (Alias: List-AzureRmApplicationGatewaySslPredefinedPolicy)
* Added redirect support in Application Gateway
    - Added Add-AzureRmApplicationGatewayRedirectConfiguration
    - Added Get-AzureRmApplicationGatewayRedirectConfiguration
    - Added New-AzureRmApplicationGatewayRedirectConfiguration
    - Added Remove-AzureRmApplicationGatewayRedirectConfiguration
    - Added Set-AzureRmApplicationGatewayRedirectConfiguration
    - Added optional parameter -RedirectConfiguration
        - Add-AzureRmApplicationGatewayRequestRoutingRule
        - New-AzureRmApplicationGatewayRequestRoutingRule
        - Set-AzureRmApplicationGatewayRequestRoutingRule
    - Added optional parameter -DefaultRedirectConfiguration
        - Add-AzureRmApplicationGatewayUrlPathMapConfig
        - New-AzureRmApplicationGatewayUrlPathMapConfig
        - Set-AzureRmApplicationGatewayUrlPathMapConfig
    - Added optional parameter -RedirectConfiguration
        - Add-AzureRmApplicationGatewayPathRuleConfig
        - New-AzureRmApplicationGatewayPathRuleConfig
        - Set-AzureRmApplicationGatewayPathRuleConfig
    - Added optional parameter -RedirectConfigurations
        - New-AzureRmApplicationGateway 
        - Set-AzureRmApplicationGateway
* Added support for azure websites in Application Gateway
    - Added New-AzureRmApplicationGatewayProbeHealthResponseMatch
    - Added optional parameters -PickHostNameFromBackendHttpSettings, -MinServers, -Match
        - Add-AzureRmApplicationGatewayProbeConfig 
        - New-AzureRmApplicationGatewayProbeConfig
        - Set-AzureRmApplicationGatewayProbeConfig
    - Added optional parameters -PickHostNameFromBackendAddress, -AffinityCookieName, -ProbeEnabled, -Path
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Update Get-AzureRmPublicIPaddress to retrieve publicipaddress resources created via VM Scale Set
* Added cmdlet to get virtual network current usage
    - Get-AzureRmVirtualNetworkUsageList

## Version 4.1.0
* Get-AzureRmNetworkUsage: New cmdlet to show network usage and capacity details
* Added new GatewaySku options for VirtualNetworkGateways
    - VpnGw1, VpnGw2, VpnGw3 are the new Skus added for Vpn gateways
* Set-AzureRmNetworkWatcherConfigFlowLog
  * Fixed  help examples
 
## Version 4.0.1

## Version 4.0.0
* Added Test-AzureRmNetworkWatcherConnectivity cmdlet
    - Returns connectivity information for a specified source VM and a destination
    - If connectivity between the source and destination cannot be established, the cmdlet returns details about the issue

## Version 3.7.0
* Added support for new web application firewall features to Application Gateways
    - Added New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig
    - Added Get-AzureRmApplicationGatewayAvailableWafRuleSets (Alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)
    - Updated New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups
    - Updated Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups

* Added support for IPSec policies to Virtual Network Gateway Connections
	- Added New-AzureRmIpsecPolicy
	- Updated New-AzureRmVirtualNetworkGatewayConnection: Added parameter -IpsecPolicies and -UsePolicyBasedTrafficSelectors

## Version 3.6.0
* Added support for connection draining to Application Gateways
    - Added Get-AzureRmApplicationGatewayConnectionDraining 
    - Added New-AzureRmApplicationGatewayConnectionDraining
    - Added Remove-AzureRmApplicationGatewayConnectionDraining 
    - Added Set-AzureRmApplicationGatewayConnectionDraining
    - Updated Add-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining
    - Updated New-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining
    - Updated Set-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining

* Remapped unused 'Name' parameter in ExpressRoute cmdlets to 'ExpressRouteCircuitName'
    - Get-AzureRmExpressRouteCircuitARPTable
    - Get-AzureRmExpressRouteCircuitRouteTable
    - Get-AzureRmExpressRouteCircuitRouteTableSummary
    - Get-AzureRmExpressRouteCircuitStats

## Version 3.5.0
* Added support for network Watcher APIs
    - New-AzureRmNetworkWatcher
    - Get-AzureRmNetworkWatcher
    - Remove-AzureRmNetworkWatcher
    - New-AzureRmPacketCaptureFilterConfig
    - New-AzureRmNetworkWatcherPacketCapture
    - Get-AzureRmNetworkWatcherPacketCapture
    - Stop-AzureRmNetworkWatcherPacketCapture
    - Remove-AzureRmNetworkWatcherPacketCapture
    - Get-AzureRmNetworkWatcherFlowLogSatus
    - Get-AzureRmNetworkWatcherNextHop
    - Get-AzureRmNetworkWatcherSecurityGroupView
    - Get-AzureRmNetworkWatcherTopology
    - Get-AzureRmNetworkWatcherTroubleshootingResult
    - Set-AzureRmNetworkWatcherConfigFlowLog
    - Start-AzureRmNetworkWatcherResourceTroubleshooting
    - Test-AzureRmNetworkWatcherIPFlow
* Add-AzureRmExpressRouteCircuitPeeringConfig
    - Added new param :-RouteFilter to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource
    - Added new param :-RouteFilterId to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource id
* New-AzureRmExpressRouteCircuitPeeringConfig
    - Added new param :-RouteFilter to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource
    - Added new param :-RouteFilterId to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource id
* Set-AzureRmExpressRouteCircuitPeeringConfig
    - Added new param :-RouteFilter to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource
    - Added new param :-RouteFilterId to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource id
* New cmdlets for selective service feature 
    - Get-AzureRmRouteFilter
    - New-AzureRmRouteFilter
    - Set-AzureRmRouteFilter
    - Remove-AzureRmRouteFilter
    - Add-AzureRmRouteFilterRuleConfig
    - Get-AzureRmRouteFilterRuleConfigobject
    - New-AzureRmRouteFilterRuleConfig
    - Set-AzureRmRouteFilterRuleConfig
    - Remove-AzureRmRouteFilterRuleConfig

## Version 3.4.0

## Version 3.3.0

## Version 3.2.0
* Get-AzureRmVirtualNetworkGatewayConnection
    - Added new param :- TunnelConnectionStatus in output Connection object to show per tunnel connection health status.
* Reset-AzureRmVirtualNetworkGateway
    - Added optional input param:- gatewayVip to pass gateway vip for ResetGateway API in case of Active-Active feature enabled gateways.
    - Gateway Vip can be retrieved from PublicIPs refered in VirtualNetworkGateway object. 

## Version 3.1.0
* Add-AzureRmVirtualNetworkPeering
    - Parameter AlloowGatewayTransit renamed to AllowGatewayTransit (an alias for the old parameter was created)
    - Fixed issue where UseRemoteGateway property was not being populated in the request to the server
* Get-AzureRmEffectiveNetworkSecurityGroup
    - Add warning if there is no response from GetEffectiveNSG
* Add Source property to EffectiveRoute 