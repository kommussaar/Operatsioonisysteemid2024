# Praktikum 13: Skriptimine Windowsis

Käesolevas praktikumis sain tuttavaks Windows PowerShell-iga (Microsofti ülesannete automatiseerimise ja konfigureerimise haldustööriist, mis koosneb käsuinterpretaatorist ja skriptimiskeelest ning on loodud .NET-raamistikus.) ning objektorienteeritud programmeerimisega. Praktikumi käigus tuli luua skript, mis päriks aruvitilt tehnilist infot. Allpool on näha praktikumi tulemus (ülesanne, koostatud skript ja skripti väljund).

Ülesanne:![image](https://github.com/user-attachments/assets/83d0d765-acbb-4ef7-a3ce-8c1ca0cb0099)


Skript: 
#$nr:	küsimuse number
#$param: mis parameetriga tegemist (võimalikult lühidalt)
#$sisu:	väljastatav sisu
function valjasta{
	param ($nr, $param, $sisu)
	$fail = "C:\Users\Marcus\Downloads\valjund.txt"
	#$aeg = Get-Date -Format "HH:mm:ss.fff"
	if($sisu -eq $null){
		$rida = "$nr.	$aeg	${param}:	NULL"
		Write-Output $rida
		$rida | Out-File -FilePath $fail -Append
	}elseif($sisu.GetType().Name -eq "Object[]"){
		$rida = "$nr.	$aeg	${param}:"
		Write-Output $rida $sisu
		$rida | Out-File -FilePath $fail -Append
		$sisu | Out-File -FilePath $fail -Append
	}else{
		$rida = "$nr.	$aeg	${param}:	$sisu"
		Write-Output $rida
		$rida | Out-File -FilePath $fail -Append
	}
}

Valjasta 1.1 "Kohalik host:" (hostname)
Valjasta 1.2 "PowerShelli versioon" $PSVersionTable.PSVersion
Valjasta 1.3 "Windowsi versioon" (Get-WmiObject -Class Win32_OperatingSystem).Version

Valjasta 2 "Võrgu konfiguratsioon (IP-aadress, võrgumask (network mask), gateway, kas DHCP on lubatud ja MAC-aadress:" (Get-WmiObject Win32_NetworkAdapterConfiguration | Select-Object IPAddress, IPSubnet, DefaultIPGateway, DHCPEnabled, MACAddress)


Valjasta 3.1 "Protsessori kirjeldus:" (Get-CimInstance Win32_Processor | Select-Object Name, Description)
Valjasta 3.2 "RAM kogus (GB):" ([math]::round((Get-CimInstance Win32_ComputerSystem).TotalPhysicalMemory /1GB, 2))

Valjasta 4 "Graafikakaardi nimi, draiveri versioon, kuupäev ja ekraani lahutus:" (Get-CimInstance Win32_VideoController | Select-Object Description, DriverVersion, DriverDate, CurrentHorizontalResolution, CurrentVerticalResolution)

Valjasta 5.1 "Partitsioonitabel:" (Get-Partition | Select-Object Disknumber, PartitionNumber, @{Name="Suurus (GB)";Expression={[math]::round($_.Size /1GB, 2)}}, Type, DriveLetter | Format-Table -AutoSize)
Valjasta 5.2 "Mitu GB on arvuti kettad mahutavuselt:" (Get-Disk | Select-Object Number, @{Name="Suurus (GB)";Expression={[math]::round($_.Size /1GB, 2)}})
Valjasta 5.3 "Mitu GB vaba ruumi on C:-kettal:" (Get-CimInstance Win32_LogicalDisk | Where-Object {$_.DeviceID -eq "C:"} | Select-Object DeviceID, @{Name="Vaba ruumi (GB)";Expression={[math]::round($_.FreeSpace /1GB, 2)}})

Valjasta 6 "PCI-siinil olevate seadmete draiverite info (kirjeldus, tootja ja versioon)" (Get-WmiObject –Class Win32_PnpSignedDriver | Where-Object {$_.DeviceID –like „PCI*“} | Select-Object Description, Manufacturer, DriverVersion | Sort-Object Description | Format-Table –AutoSize)

Valjasta 7 "Arvutis olevad kasutajad (nimi, kirjeldus, kas on lokaalne kasutaja (LocalAccount) ja kas on keelatud (Disabled)):" (Get-CimInstance Win32_UserAccount | Select-Object Name, Description, LocalAccount, Disabled | Format-Table -AutoSize)

Valjasta 8 "Käimasolevate protsesside arv:" ((Get-Process).count)

Valjasta 9 "10 viimasena käivitatud protsessi (nimi, PID ja käivitamise aeg (StartTime))." (Get-Process | Where-Object {$_.StartTime -ne $null} | Sort-Object StartTime -Descending | Select-Object -First 10 | Format-Table Name, Id, StartTime)

Valjasta 10 "Arvuti kuupäev ja kellaaeg:" (Get-Date)

Skipti väljund: 
1.1.		Kohalik host::	KOMMUSSAAR-W11
1.2.		PowerShelli versioon:	5.1.22621.4391
1.3.		Windowsi versioon:	10.0.22631
2.		Võrgu konfiguratsioon (IP-aadress, võrgumask (network mask), gateway, kas DHCP on lubatud ja MAC-aadress::


IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : True
MACAddress       : 

IPAddress        : {10.0.2.15, fe80::b4c7:7a59:dc95:c92, fd00::6073:2c22:6b0e:2720, fd00::53c2:7d1c:54f0:cd77}
IPSubnet         : {255.255.255.0, 64, 128, 64}
DefaultIPGateway : {10.0.2.2, fe80::2}
DHCPEnabled      : True
MACAddress       : 08:00:27:FF:E0:87

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 

IPAddress        : 
IPSubnet         : 
DefaultIPGateway : 
DHCPEnabled      : False
MACAddress       : 



3.1.		Protsessori kirjeldus::	@{Name=AMD Ryzen 5 3500U with Radeon Vega Mobile Gfx  ; Description=AMD64 Family 23 Model 24 Stepping 1}
3.2.		RAM kogus (GB)::	4.98
4.		Graafikakaardi nimi, draiveri versioon, kuupäev ja ekraani lahutus::	@{Description=VirtualBox Graphics Adapter (WDDM); DriverVersion=7.1.4.15100; DriverDate=10/10/2024 03:00:00; CurrentHorizontalResolution=1920; CurrentVerticalResolution=966}
5.1.		Partitsioonitabel::

Disknumber PartitionNumber Suurus (GB) Type     DriveLetter
---------- --------------- ----------- ----     -----------
         0               1         0,1 System              
         0               2        0,02 Reserved            
         0               3       63,13 Basic              C
         0               4        0,75 Recovery            
         1               1        0,02 Reserved            
         1               2     3906,23 Basic              I


5.2.		Mitu GB on arvuti kettad mahutavuselt::

Number Suurus (GB)
------ -----------
     0          64
     1     3906,25


5.3.		Mitu GB vaba ruumi on C:-kettal::	@{DeviceID=C:; Vaba ruumi (GB)=32.12}
6.		PCI-siinil olevate seadmete draiverite info (kirjeldus, tootja ja versioon):

Description                          Manufacturer                     DriverVersion  
-----------                          ------------                     -------------  
CPU to PCI Bridge                    Intel                            10.0.22621.1   
High Definition Audio Controller     Microsoft                        10.0.22621.4391
Intel(R) PRO/1000 MT Desktop Adapter Intel                            8.4.13.0       
PCI to ISA Bridge                    Intel                            10.0.22621.1   
Standard SATA AHCI Controller        Standard SATA AHCI Controller    10.0.22621.2506
USB xHCI Compliant Host Controller   Generic USB xHCI Host Controller 10.0.22621.4541
VirtualBox Graphics Adapter (WDDM)   Oracle Corporation               7.1.4.15100    
VirtualBox Guest Device              Oracle Corporation               7.1.4.15100    


7.		Arvutis olevad kasutajad (nimi, kirjeldus, kas on lokaalne kasutaja (LocalAccount) ja kas on keelatud (Disabled))::

Name               Description                                                                                     LocalAccount Disabled
----               -----------                                                                                     ------------ --------
Administrator      Built-in account for administering the computer/domain                                                  True     True
DefaultAccount     A user account managed by the system.                                                                   True     True
Guest              Built-in account for guest access to the computer/domain                                                True     True
Marcus                                                                                                                     True    False
Marcus-tava                                                                                                                True    False
tootaja1                                                                                                                   True    False
tootaja2                                                                                                                   True    False
WDAGUtilityAccount A user account managed and used by the system for Windows Defender Application Guard scenarios.         True     True
ylemus                                                                                                                     True    False


8.		Käimasolevate protsesside arv::	151
9.		10 viimasena käivitatud protsessi (nimi, PID ja käivitamise aeg (StartTime)).:

Name                 Id StartTime          
----                 -- ---------          
SearchFilterHost   3972 25.12.2024 23:51:56
SearchProtocolHost 1012 25.12.2024 23:51:56
svchost            8584 25.12.2024 23:44:14
svchost            8252 25.12.2024 23:44:13
WmiPrvSE           6700 25.12.2024 23:43:56
svchost            3788 25.12.2024 23:40:58
smartscreen        5948 25.12.2024 23:39:45
svchost            2776 25.12.2024 22:16:57
MoNotificationUx   6840 25.12.2024 21:54:53
RuntimeBroker      8340 25.12.2024 21:14:12


10.		Arvuti kuupäev ja kellaaeg::	12/25/2024 23:51:59

