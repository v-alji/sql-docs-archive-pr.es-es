---
title: Método GenerateDatabaseRightsScript (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseRightsScript method
ms.assetid: f2e6dcc9-978f-4c2c-bafe-36c330247fd0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 768e73d13d3b06f7913c3c816fded1b28c56199f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748585"
---
# <a name="generatedatabaserightsscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4d2e3-102">Método GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="4d2e3-102">GenerateDatabaseRightsScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4d2e3-103">Genera un script SQL que se puede usar para conceder derechos a un usuario sobre la base de datos del servidor de informes y otras bases de datos necesarias para el funcionamiento de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-103">Generates a SQL Script that can be used to grant a user rights to the report server database and other databases required for a report server to run.</span></span> <span data-ttu-id="4d2e3-104">Se espera que el autor de la llamada se conecte al servidor de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-104">The caller is expected to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and execute the script.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d2e3-105">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseRightsScript(ByVal UserName As String, _  
    ByVal DatabaseName As String, ByVal IsRemote As Boolean, _  
    ByVal IsWindowsUser As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseRightsScript(string UserName, string DatabaseName, bool IsRemote, bool IsWindowsUser, out string Script,   
out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d2e3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d2e3-106">Parameters</span></span>  
 <span data-ttu-id="4d2e3-107">*UserName*</span><span class="sxs-lookup"><span data-stu-id="4d2e3-107">*UserName*</span></span>  
 <span data-ttu-id="4d2e3-108">Nombre de usuario o identificador de seguridad de Windows (SID) del usuario al que el script concederá derechos.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-108">The user name or Windows security identifier (SID) of the user to which the script will grant rights.</span></span>  
  
 <span data-ttu-id="4d2e3-109">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="4d2e3-109">*DatabaseName*</span></span>  
 <span data-ttu-id="4d2e3-110">Nombre de base de datos para el que el script concederá acceso al usuario.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-110">The database name to which the script will grant access to the user.</span></span>  
  
 <span data-ttu-id="4d2e3-111">*IsRemote*</span><span class="sxs-lookup"><span data-stu-id="4d2e3-111">*IsRemote*</span></span>  
 <span data-ttu-id="4d2e3-112">Valor booleano que indica si la base de datos es remota desde el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-112">A Boolean value to indicating whether the database is remote from the report server.</span></span>  
  
 <span data-ttu-id="4d2e3-113">*IsWindowsUser*</span><span class="sxs-lookup"><span data-stu-id="4d2e3-113">*IsWindowsUser*</span></span>  
 <span data-ttu-id="4d2e3-114">Valor booleano que indica si el nombre de usuario especificado es un usuario de Windows o un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d2e3-114">A Boolean value indicating whether the specified user name is a Windows user or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="4d2e3-115">*Script*</span><span class="sxs-lookup"><span data-stu-id="4d2e3-115">*Script*</span></span>  
 <span data-ttu-id="4d2e3-116">[out] Una cadena que contiene el script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generado.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-116">[out] A string containing the generated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span>  
  
 <span data-ttu-id="4d2e3-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4d2e3-117">*HRESULT*</span></span>  
 <span data-ttu-id="4d2e3-118">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d2e3-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d2e3-119">Return Value</span></span>  
 <span data-ttu-id="4d2e3-120">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-120">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4d2e3-121">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-121">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4d2e3-122">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-122">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d2e3-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d2e3-123">Remarks</span></span>  
 <span data-ttu-id="4d2e3-124">Si *DatabaseName* está vacío, *IsRemote* se omite y el valor del archivo de configuración del servidor de informes se usa para el nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-124">If *DatabaseName* is empty then *IsRemote* is ignored and the report server configuration file value is used for the database name.</span></span>  
  
 <span data-ttu-id="4d2e3-125">Si *IsWindowsUser* se establece en `true` , el *nombre de usuario* debe tener el formato \<domain> \\<nombre de usuario \> .</span><span class="sxs-lookup"><span data-stu-id="4d2e3-125">If *IsWindowsUser* is set to `true`, *UserName* should be in the format \<domain>\\<username\>.</span></span>  
  
 <span data-ttu-id="4d2e3-126">Cuando *IsWindowsUser* se establece en `true` , el script generado concede derechos de inicio de sesión al usuario para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , estableciendo la base de datos del servidor de informes como la base de datos predeterminada, y concede el rol **RSExec** en la base de datos del servidor de informes, la base de datos temporal del servidor de informes, la base de datos maestra y la base de datos del sistema msdb.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-126">When *IsWindowsUser* is set to `true`, the generated script grants login rights to the user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], setting the report server database as the default database, and grants the **RSExec** role on the report server database, the report server temporary database, the master database and the MSDB system database.</span></span>  
  
 <span data-ttu-id="4d2e3-127">Cuando *IsWindowsUser* se establece en `true` , el método acepta los SID de Windows estándar como entrada.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-127">When *IsWindowsUser* is set to `true`, the method accepts standard Windows SIDs as input.</span></span> <span data-ttu-id="4d2e3-128">Cuando se proporciona un SID de Windows estándar o el nombre de la cuenta de servicio, se traduce a una cadena de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-128">When a standard Windows SID or service account name is supplied, it is translated to a user name string.</span></span> <span data-ttu-id="4d2e3-129">Si la base de datos es local, la cuenta se traduce a la representación localizada correcta de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-129">If the database is local, the account is translated to the correct localized representation of the account.</span></span> <span data-ttu-id="4d2e3-130">Si la base de datos es remota, la cuenta se representa como la cuenta del equipo.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-130">If the database is remote, the account is represented as the computer's account.</span></span>  
  
 <span data-ttu-id="4d2e3-131">En la tabla siguiente, se muestran las cuentas que están traducidas y su representación remota.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-131">The following table shows accounts that are translated and their remote representation.</span></span>  
  
|<span data-ttu-id="4d2e3-132">Cuenta / SID traducido</span><span class="sxs-lookup"><span data-stu-id="4d2e3-132">Account / SID that is translated</span></span>|<span data-ttu-id="4d2e3-133">Nombre común</span><span class="sxs-lookup"><span data-stu-id="4d2e3-133">Common Name</span></span>|<span data-ttu-id="4d2e3-134">Nombre remoto</span><span class="sxs-lookup"><span data-stu-id="4d2e3-134">Remote Name</span></span>|  
|---------------------------------------|-----------------|-----------------|  
|<span data-ttu-id="4d2e3-135">(S-1-5-18)</span><span class="sxs-lookup"><span data-stu-id="4d2e3-135">(S-1-5-18)</span></span>|<span data-ttu-id="4d2e3-136">Sistema local</span><span class="sxs-lookup"><span data-stu-id="4d2e3-136">Local System</span></span>|<span data-ttu-id="4d2e3-137">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="4d2e3-137">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="4d2e3-138">.\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="4d2e3-138">.\LocalSystem</span></span>|<span data-ttu-id="4d2e3-139">Sistema local</span><span class="sxs-lookup"><span data-stu-id="4d2e3-139">Local System</span></span>|<span data-ttu-id="4d2e3-140">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="4d2e3-140">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="4d2e3-141">NombreDeEquipo\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="4d2e3-141">ComputerName\LocalSystem</span></span>|<span data-ttu-id="4d2e3-142">Sistema local</span><span class="sxs-lookup"><span data-stu-id="4d2e3-142">Local System</span></span>|<span data-ttu-id="4d2e3-143">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="4d2e3-143">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="4d2e3-144">LocalSystem (Sistema local)</span><span class="sxs-lookup"><span data-stu-id="4d2e3-144">LocalSystem</span></span>|<span data-ttu-id="4d2e3-145">Sistema local</span><span class="sxs-lookup"><span data-stu-id="4d2e3-145">Local System</span></span>|<span data-ttu-id="4d2e3-146">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="4d2e3-146">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="4d2e3-147">(S-1-5-20)</span><span class="sxs-lookup"><span data-stu-id="4d2e3-147">(S-1-5-20)</span></span>|<span data-ttu-id="4d2e3-148">Servicio de red</span><span class="sxs-lookup"><span data-stu-id="4d2e3-148">Network Service</span></span>|<span data-ttu-id="4d2e3-149">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="4d2e3-149">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="4d2e3-150">NT AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="4d2e3-150">NT AUTHORITY\NetworkService</span></span>|<span data-ttu-id="4d2e3-151">Servicio de red</span><span class="sxs-lookup"><span data-stu-id="4d2e3-151">Network Service</span></span>|<span data-ttu-id="4d2e3-152">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="4d2e3-152">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="4d2e3-153">(S-1-5-19)</span><span class="sxs-lookup"><span data-stu-id="4d2e3-153">(S-1-5-19)</span></span>|<span data-ttu-id="4d2e3-154">Servicio local</span><span class="sxs-lookup"><span data-stu-id="4d2e3-154">Local Service</span></span>|<span data-ttu-id="4d2e3-155">Error: vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-155">Error - see below.</span></span>|  
|<span data-ttu-id="4d2e3-156">NT AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="4d2e3-156">NT AUTHORITY\LocalService</span></span>|<span data-ttu-id="4d2e3-157">Servicio local</span><span class="sxs-lookup"><span data-stu-id="4d2e3-157">Local Service</span></span>|<span data-ttu-id="4d2e3-158">Error: vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-158">Error - see below.</span></span>|  
  
 <span data-ttu-id="4d2e3-159">En [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], si está utilizando una cuenta integrada y la base de datos del servidor de informes es remota, se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-159">On [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], if you are using a built-in account and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="4d2e3-160">Si se especifica la cuenta integrada `LocalService` y la base de datos del servidor de informes es remota, se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-160">If the `LocalService` built-in account is specified and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="4d2e3-161">Cuando *IsWindowsUser* es verdadero y el valor proporcionado en *UserName* debe traducirse, el proveedor WMI determina si la base de datos del servidor de informes se encuentra en el mismo equipo o en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-161">When *IsWindowsUser* is true and the value supplied in *UserName* needs to be translated, the WMI provider determines whether the report server database is located on the same computer or on a remote computer.</span></span> <span data-ttu-id="4d2e3-162">Para determinar si la instalación es local, el proveedor WMI evalúa la propiedad DatabaseServerName con la lista siguiente de valores.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-162">To determine if the installation is local, the WMI provider evaluates the DatabaseServerName property against the following list of values.</span></span> <span data-ttu-id="4d2e3-163">Si se encuentra una coincidencia, la base de datos es local.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-163">If a match is found, the database is local.</span></span> <span data-ttu-id="4d2e3-164">De lo contrario, es remota.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-164">Otherwise, it is remote.</span></span> <span data-ttu-id="4d2e3-165">La comparación distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-165">The comparison is case-insensitive.</span></span>  
  
|<span data-ttu-id="4d2e3-166">Valor de DatabaseServerName</span><span class="sxs-lookup"><span data-stu-id="4d2e3-166">Value of DatabaseServerName</span></span>|<span data-ttu-id="4d2e3-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d2e3-167">Example</span></span>|  
|---------------------------------|-------------|  
|<span data-ttu-id="4d2e3-168">"."</span><span class="sxs-lookup"><span data-stu-id="4d2e3-168">"."</span></span>||  
|<span data-ttu-id="4d2e3-169">"(local)"</span><span class="sxs-lookup"><span data-stu-id="4d2e3-169">"(local)"</span></span>||  
|<span data-ttu-id="4d2e3-170">"LOCAL"</span><span class="sxs-lookup"><span data-stu-id="4d2e3-170">"LOCAL"</span></span>||  
|<span data-ttu-id="4d2e3-171">localhost</span><span class="sxs-lookup"><span data-stu-id="4d2e3-171">localhost</span></span>||  
|\<Machinename>|<span data-ttu-id="4d2e3-172">testlab14</span><span class="sxs-lookup"><span data-stu-id="4d2e3-172">testlab14</span></span>|  
|\<MachineFQDN>|<span data-ttu-id="4d2e3-173">example.redmond.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4d2e3-173">example.redmond.microsoft.com</span></span>|  
|\<IPAddress>|<span data-ttu-id="4d2e3-174">180.012.345,678</span><span class="sxs-lookup"><span data-stu-id="4d2e3-174">180.012.345,678</span></span>|  
  
 <span data-ttu-id="4d2e3-175">Cuando *IsWindowsUser* se establece en `true` , el proveedor WMI llama a LookupAccountName para obtener el SID de la cuenta y, a continuación, llama a LookupAccountSID para obtener el nombre que se va a colocar en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-175">When *IsWindowsUser* is set to `true`, the WMI provider calls LookupAccountName to get the SID for the account and then calls LookupAccountSID to get the name to put in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span> <span data-ttu-id="4d2e3-176">Esto asegura que el nombre de la cuenta que se utiliza pasará la validación [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d2e3-176">This ensures that the account name used will pass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validation.</span></span>  
  
 <span data-ttu-id="4d2e3-177">Cuando *IsWindowsUser* se establece en `false` , el script generado concede el rol **RSExec** en la base de datos del servidor de informes, la base de datos temporal del servidor de informes y la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-177">When *IsWindowsUser* is set to `false`, the generated script grants the **RSExec** role on the report server database, the report server temporary database, and the MSDB database.</span></span>  
  
 <span data-ttu-id="4d2e3-178">Cuando *IsWindowsUser* se establece en `false` , el usuario SQL Server debe existir en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que el script se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-178">When *IsWindowsUser* is set to `false`, the SQL Server user must already exist on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the script to run successfully.</span></span>  
  
 <span data-ttu-id="4d2e3-179">Si el servidor de informes no cuenta con una base de datos del servidor de informes especificada, al llamar a GrantRightsToDatabaseUser se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-179">If the report server does not have a report server database specified, calling GrantRightsToDatabaseUser returns an error.</span></span>  
  
 <span data-ttu-id="4d2e3-180">El script generado admite [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 y [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d2e3-180">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d2e3-181">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d2e3-181">Requirements</span></span>  
 <span data-ttu-id="4d2e3-182">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d2e3-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2e3-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d2e3-183">See Also</span></span>  
 [<span data-ttu-id="4d2e3-184">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4d2e3-184">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
