---
title: Clase SqlErrorLogEvent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 358b6906e422be2984f2ebdbde636ad0b8376993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671955"
---
# <a name="sqlerrorlogevent-class"></a><span data-ttu-id="5189f-102">SqlErrorLogEvent, clase</span><span class="sxs-lookup"><span data-stu-id="5189f-102">SqlErrorLogEvent Class</span></span>
  <span data-ttu-id="5189f-103">Proporciona las propiedades para ver los eventos en un archivo de registro [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificado.</span><span class="sxs-lookup"><span data-stu-id="5189f-103">Provides properties for viewing events in a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5189f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5189f-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="5189f-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5189f-105">Properties</span></span>  
 <span data-ttu-id="5189f-106">La clase SQLErrorLogEvent define las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="5189f-106">The SQLErrorLogEvent class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5189f-107">FileName</span><span class="sxs-lookup"><span data-stu-id="5189f-107">FileName</span></span>|<span data-ttu-id="5189f-108">Tipo de datos: `string`</span><span class="sxs-lookup"><span data-stu-id="5189f-108">Data type: `string`</span></span><br /><br /> <span data-ttu-id="5189f-109">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5189f-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="5189f-110">El nombre del archivo de registro de errores.</span><span class="sxs-lookup"><span data-stu-id="5189f-110">The name of the error log file.</span></span>|  
|<span data-ttu-id="5189f-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="5189f-111">InstanceName</span></span>|<span data-ttu-id="5189f-112">Tipo de datos: `string`</span><span class="sxs-lookup"><span data-stu-id="5189f-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="5189f-113">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5189f-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="5189f-114">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="5189f-114">Qualifiers: Key</span></span><br /><br /> <span data-ttu-id="5189f-115">El nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde reside el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5189f-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="5189f-116">LogDate</span><span class="sxs-lookup"><span data-stu-id="5189f-116">LogDate</span></span>|<span data-ttu-id="5189f-117">Tipo de datos: `datetime`</span><span class="sxs-lookup"><span data-stu-id="5189f-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="5189f-118">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5189f-118">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="5189f-119">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="5189f-119">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="5189f-120">Fecha y hora en que el evento se grabó en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5189f-120">The date and time that the event was recorded in the log file.</span></span>|  
|<span data-ttu-id="5189f-121">Message</span><span class="sxs-lookup"><span data-stu-id="5189f-121">Message</span></span>|<span data-ttu-id="5189f-122">Tipo de datos: `string`</span><span class="sxs-lookup"><span data-stu-id="5189f-122">Data type: `string`</span></span><br /><br /> <span data-ttu-id="5189f-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5189f-123">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="5189f-124">Mensaje del evento.</span><span class="sxs-lookup"><span data-stu-id="5189f-124">The event message.</span></span>|  
|<span data-ttu-id="5189f-125">ProcessInfo</span><span class="sxs-lookup"><span data-stu-id="5189f-125">ProcessInfo</span></span>|<span data-ttu-id="5189f-126">Tipo de datos: `string`</span><span class="sxs-lookup"><span data-stu-id="5189f-126">Data type: `string`</span></span><br /><br /> <span data-ttu-id="5189f-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5189f-127">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="5189f-128">Información sobre el identificador del proceso del servidor de origen (SPID) para el evento.</span><span class="sxs-lookup"><span data-stu-id="5189f-128">Information about the source server process ID (SPID) for the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5189f-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5189f-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5189f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="5189f-130">MOF</span></span>|<span data-ttu-id="5189f-131">Sqlmgmproviderxpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="5189f-131">Sqlmgmproviderxpsp2up.mof</span></span>|  
|<span data-ttu-id="5189f-132">Archivo DLL</span><span class="sxs-lookup"><span data-stu-id="5189f-132">DLL</span></span>|<span data-ttu-id="5189f-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="5189f-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="5189f-134">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="5189f-134">Namespace</span></span>|<span data-ttu-id="5189f-135">\raíz\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="5189f-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5189f-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5189f-136">Example</span></span>  
 <span data-ttu-id="5189f-137">En el siguiente ejemplo se muestra cómo recuperar los valores para todos los eventos anotados en un archivo de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="5189f-137">The following example shows how to retrieve values for all logged events in a specified log file.</span></span> <span data-ttu-id="5189f-138">Para ejecutar el ejemplo, reemplace \<*Instance_Name*> por el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , como ' Instance1 ', y reemplace ' File_Name ' por el nombre del archivo de registro de errores, como ' ERRORLOG. 1 '.</span><span class="sxs-lookup"><span data-stu-id="5189f-138">To run the example, replace \<*Instance_Name*> with the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as 'Instance1', and replace 'File_Name' with the name of the error log file, such as 'ERRORLOG.1'.</span></span>  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a><span data-ttu-id="5189f-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5189f-139">Comments</span></span>  
 <span data-ttu-id="5189f-140">Cuando no se proporciona *InstanceName* o *filename* en la instrucción WQL, la consulta devolverá información para la instancia predeterminada y el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivo de registro actual.</span><span class="sxs-lookup"><span data-stu-id="5189f-140">When *InstanceName* or *FileName* are not provided in the WQL statement, the query will return information for the default instance and the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span> <span data-ttu-id="5189f-141">Por ejemplo, la siguiente instrucción WQL devolverá todos los eventos de registro del archivo de registro actual (ERRORLOG) en la instancia predeterminada (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="5189f-141">For example, the following WQL statement will return all log events from the current log file (ERRORLOG) on the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a><span data-ttu-id="5189f-142">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5189f-142">Security</span></span>  
 <span data-ttu-id="5189f-143">Para conectarse a un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivo de registro a través de WMI, debe tener los siguientes permisos en los equipos locales y remotos:</span><span class="sxs-lookup"><span data-stu-id="5189f-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="5189f-144">Acceso de lectura al espacio de nombres WMI **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="5189f-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="5189f-145">De forma predeterminada, todos tienen acceso de lectura mediante el permiso Habilitar cuenta.</span><span class="sxs-lookup"><span data-stu-id="5189f-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
-   <span data-ttu-id="5189f-146">Permiso de lectura a la carpeta que contiene los registros de errores.</span><span class="sxs-lookup"><span data-stu-id="5189f-146">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="5189f-147">De forma predeterminada, los registros de errores se encuentran en la siguiente ruta de acceso (donde \<*Drive> \* representa la unidad donde se instaló [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y \<*InstanceName*> es el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="5189f-147">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="5189f-148">\*\* \<Drive> : \Archivos de Programa\microsoft SQL Server\MSSQL12\*\* **. \<InstanceName> \Mssql\log.**</span><span class="sxs-lookup"><span data-stu-id="5189f-148">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="5189f-149">Si se conecta a través de un firewall, asegúrese de que se establece una excepción en el firewall para WMI en los equipos de destino remotos.</span><span class="sxs-lookup"><span data-stu-id="5189f-149">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="5189f-150">Para obtener más información, consulte [conectarse a WMI de forma remota a partir de Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="5189f-150">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5189f-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5189f-151">See Also</span></span>  
 <span data-ttu-id="5189f-152">[Clase SqlErrorLogFile](sqlerrorlogfile-class.md) </span><span class="sxs-lookup"><span data-stu-id="5189f-152">[SqlErrorLogFile Class](sqlerrorlogfile-class.md) </span></span>  
 [<span data-ttu-id="5189f-153">Ver archivos del registro sin conexión</span><span class="sxs-lookup"><span data-stu-id="5189f-153">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
