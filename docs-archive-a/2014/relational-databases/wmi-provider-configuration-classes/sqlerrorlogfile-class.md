---
title: Clase SqlErrorLogFile | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
ms.assetid: 2b83ae4a-c0d4-414c-b6e5-a41ec7c13159
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d73f97ebddd7a1d18c73a2cbce7fe79dafc17a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744567"
---
# <a name="sqlerrorlogfile-class"></a><span data-ttu-id="7024b-102">Clase SqlErrorLogFile</span><span class="sxs-lookup"><span data-stu-id="7024b-102">SqlErrorLogFile Class</span></span>
  <span data-ttu-id="7024b-103">Proporciona propiedades para ver información sobre un archivo de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7024b-103">Provides properties for viewing information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7024b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7024b-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogFile  
{  
   uint32ArchiveNumber;  
   stringInstanceName;  
   datetimeLastModified;  
   uint32LogFileSize;  
   stringName;  
  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="7024b-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7024b-105">Properties</span></span>  
 <span data-ttu-id="7024b-106">La clase SQLErrorLogFile define las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="7024b-106">The SQLErrorLogFile class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7024b-107">ArchiveNumber</span><span class="sxs-lookup"><span data-stu-id="7024b-107">ArchiveNumber</span></span>|<span data-ttu-id="7024b-108">Tipo de datos: `uint32`</span><span class="sxs-lookup"><span data-stu-id="7024b-108">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="7024b-109">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7024b-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="7024b-110">El número de archivo para el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="7024b-110">The archive number for the log file.</span></span>|  
|<span data-ttu-id="7024b-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="7024b-111">InstanceName</span></span>|<span data-ttu-id="7024b-112">Tipo de datos: `string`</span><span class="sxs-lookup"><span data-stu-id="7024b-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="7024b-113">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7024b-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="7024b-114">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="7024b-114">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="7024b-115">El nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde reside el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="7024b-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="7024b-116">LastModified</span><span class="sxs-lookup"><span data-stu-id="7024b-116">LastModified</span></span>|<span data-ttu-id="7024b-117">Tipo de datos: `datetime`</span><span class="sxs-lookup"><span data-stu-id="7024b-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="7024b-118">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7024b-118">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="7024b-119">Fecha de la última modificación del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="7024b-119">The date that the log file was last modified.</span></span>|  
|<span data-ttu-id="7024b-120">LogFileSize</span><span class="sxs-lookup"><span data-stu-id="7024b-120">LogFileSize</span></span>|<span data-ttu-id="7024b-121">Tipo de datos: `uint32`</span><span class="sxs-lookup"><span data-stu-id="7024b-121">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="7024b-122">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7024b-122">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="7024b-123">El tamaño del archivo de registro en bytes.</span><span class="sxs-lookup"><span data-stu-id="7024b-123">The log file size, in bytes.</span></span>|  
|<span data-ttu-id="7024b-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="7024b-124">Name</span></span>|<span data-ttu-id="7024b-125">Tipo de datos: `string`</span><span class="sxs-lookup"><span data-stu-id="7024b-125">Data type: `string`</span></span><br /><br /> <span data-ttu-id="7024b-126">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7024b-126">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="7024b-127">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="7024b-127">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="7024b-128">El nombre del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="7024b-128">The name of the log file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7024b-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7024b-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7024b-130">MOF</span><span class="sxs-lookup"><span data-stu-id="7024b-130">MOF</span></span>|<span data-ttu-id="7024b-131">Sqlmgmprovider xpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="7024b-131">Sqlmgmprovider xpsp2up.mof</span></span>|  
|<span data-ttu-id="7024b-132">Archivo DLL</span><span class="sxs-lookup"><span data-stu-id="7024b-132">DLL</span></span>|<span data-ttu-id="7024b-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="7024b-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="7024b-134">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="7024b-134">Namespace</span></span>|<span data-ttu-id="7024b-135">\raíz\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="7024b-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7024b-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7024b-136">Example</span></span>  
 <span data-ttu-id="7024b-137">En el siguiente ejemplo se recupera información sobre todos los archivos de registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7024b-137">The following example retrieves information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7024b-138">Para ejecutar el ejemplo, reemplace \<*Instance_Name*> por el nombre de la instancia, por ejemplo, ' Instance1 '.</span><span class="sxs-lookup"><span data-stu-id="7024b-138">To run the example, replace \<*Instance_Name*> with the name of the instance, for example, 'Instance1'.</span></span>  
  
```  
on error resume next  
set strComputer = "."  
set objWMIService = GetObject("winmgmts:\\.\root\Microsoft\SqlServer\ComputerManagement10")  
set LogFiles = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogFile WHERE InstanceName = '<Instance_Name>'")  
  
For Each logFile in LogFiles  
  
WScript.Echo "Instance Name:  " & logFile.InstanceName & vbNewLine _  
    & "Log File Name:  " & logFile.Name & vbNewLine _  
    & "Archive Number: " & logFile.ArchiveNumber & vbNewLine _  
    & "Log File Size:  " & logFile.LogFileSize & " bytes" & vbNewLine _  
    & "Last Modified:  " & logFile.LastModified & vbNewLine _  
  
Next   
```  
  
## <a name="comments"></a><span data-ttu-id="7024b-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7024b-139">Comments</span></span>  
 <span data-ttu-id="7024b-140">Cuando no se proporciona *InstanceName* en la instrucción WQL, la consulta devolverá información para la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7024b-140">When *InstanceName* is not provided in the WQL statement, the query will return information for the default instance.</span></span> <span data-ttu-id="7024b-141">Por ejemplo, la siguiente instrucción WQL devolverá información sobre todos los archivos de registro de la instancia predeterminada (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="7024b-141">For example, the following WQL statement will return information about all log files from the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogFile"  
```  
  
## <a name="security"></a><span data-ttu-id="7024b-142">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7024b-142">Security</span></span>  
 <span data-ttu-id="7024b-143">Para conectarse a un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivo de registro a través de WMI, debe tener los siguientes permisos en los equipos locales y remotos:</span><span class="sxs-lookup"><span data-stu-id="7024b-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="7024b-144">Acceso de lectura al espacio de nombres WMI **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="7024b-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="7024b-145">De forma predeterminada, todos tienen acceso de lectura mediante el permiso Habilitar cuenta.</span><span class="sxs-lookup"><span data-stu-id="7024b-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7024b-146">Para obtener información sobre cómo comprobar los permisos de WMI, consulte la sección seguridad del tema [ver archivos de registro sin conexión](../logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="7024b-146">For information about how to verify WMI permissions, see the Security section of the topic [View Offline Log Files](../logs/view-offline-log-files.md).</span></span>  
  
-   <span data-ttu-id="7024b-147">Permiso de lectura a la carpeta que contiene los registros de errores.</span><span class="sxs-lookup"><span data-stu-id="7024b-147">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="7024b-148">De forma predeterminada, los registros de errores se encuentran en la siguiente ruta de acceso (donde \<*Drive> \* representa la unidad donde se instaló [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y \<*InstanceName*> es el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="7024b-148">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="7024b-149">\*\* \<Drive> : \Archivos de Programa\microsoft SQL Server\MSSQL11\*\* **. \<InstanceName> \Mssql\log.**</span><span class="sxs-lookup"><span data-stu-id="7024b-149">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL11** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="7024b-150">Si se conecta a través de un firewall, asegúrese de que se establece una excepción en el firewall para WMI en los equipos de destino remotos.</span><span class="sxs-lookup"><span data-stu-id="7024b-150">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="7024b-151">Para obtener más información, consulte [conectarse a WMI de forma remota a partir de Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="7024b-151">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7024b-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7024b-152">See Also</span></span>  
 <span data-ttu-id="7024b-153">[Clase SqlErrorLogEvent](sqlerrorlogevent-class.md) </span><span class="sxs-lookup"><span data-stu-id="7024b-153">[SqlErrorLogEvent Class](sqlerrorlogevent-class.md) </span></span>  
 [<span data-ttu-id="7024b-154">Ver archivos del registro sin conexión</span><span class="sxs-lookup"><span data-stu-id="7024b-154">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
