---
title: Actualizar ensamblados de SQLCLR después de actualizar .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b1a008cc-7e6b-4655-a869-bd429f986400
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45d60db413e11828f26bd03e1c8f350645838d12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673911"
---
# <a name="upgrade-sqlclr-assemblies-after-net-framework-update"></a><span data-ttu-id="c35a3-102">Actualizar ensamblados de SQLCLR después de actualizar .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c35a3-102">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>
  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] <span data-ttu-id="c35a3-103">(DQS) es una colección de rutinas de Common Language Runtime de SQL (SQLCR) que hacen referencia a los ensamblados de Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c35a3-103">(DQS) is a collection of SQL Common Language Runtime (SQLCR) routines that reference Microsoft .NET Framework 4 assemblies.</span></span> <span data-ttu-id="c35a3-104">Al instalar actualizaciones de .NET Framework en el equipo que afecten al ensamblado de .NET Framework al que hacen referencia, se producirá un cambio en el identificador de versión de módulos (MVID) del ensamblado en la memoria caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="c35a3-104">When you install any .NET Framework updates on your computer that affect any such referenced .NET Framework assembly, it leads to a change in the Module Version ID (MVID) of the assembly in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="c35a3-105">Esto produce una incoherencia entre los MVID del ensamblado al que se hace referencia en la GAC y el ensamblado de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c35a3-105">This causes a mismatch between the MVIDs of the referenced assembly in GAC and the assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="c35a3-106">Si la actualización de .NET Framework requiere reiniciar el equipo [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , los ensamblados SQLCLR afectados se actualizan automáticamente para corregir el problema de discrepancia de MVID en el reinicio del equipo [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c35a3-106">If the .NET Framework update requires you to restart the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, the affected SQLCLR assemblies are upgraded automatically to fix the MVID mismatch issue on restarting the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span> <span data-ttu-id="c35a3-107">Sin embargo, para las actualizaciones de .NET Framework que no necesitan reiniciar el equipo con [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , se produce un error debido a una discrepancia en los MVID de los ensamblados al intentar conectarse a un [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] mediante un [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c35a3-107">However, for .NET Framework updates that do not require you to restart your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, an error occurs due to the mismatch in the MVIDs of the assemblies when you try to connect to a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] using a [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span></span>  
  
```  
A new version of .NET was installed on this machine. In order to continue to work with DQS please run dqsinstaller.exe -upgradedlls.  
```  
  
 <span data-ttu-id="c35a3-108">Para corregir este problema, deben actualizarse los ensamblados SQLCLR afectados en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c35a3-108">To fix this issue, the affected SQLCLR assemblies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be upgraded.</span></span> <span data-ttu-id="c35a3-109">Puede hacerlo ejecutando el archivo DQSInstaller.exe con el parámetro de línea de comandos **upgradedlls** para omitir la reconstrucción de las bases de datos de DQS y actualizar solo los ensamblados afectados.</span><span class="sxs-lookup"><span data-stu-id="c35a3-109">You can do so by running the DQSInstaller.exe file with the **upgradedlls** command line parameter to skip recreating the DQS databases, and just upgrade the affected assemblies.</span></span> <span data-ttu-id="c35a3-110">Esto garantiza que se conserven las bases de conocimiento, los proyectos de calidad de datos y otros datos de DQS.</span><span class="sxs-lookup"><span data-stu-id="c35a3-110">This ensures that your knowledge bases, data quality projects, and any other data in DQS are preserved.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c35a3-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c35a3-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="c35a3-112">Debe haber iniciado sesión como miembro del grupo Administradores en el equipo con [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c35a3-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="c35a3-113">La cuenta de usuario de Windows debe ser miembro del rol fijo de servidor sysadmin en la instancia de SQL Server donde está instalado [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c35a3-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-sqlclr-assemblies"></a><span data-ttu-id="c35a3-114">Para actualizar ensamblados de SQLCLR</span><span class="sxs-lookup"><span data-stu-id="c35a3-114">To upgrade SQLCLR Assemblies</span></span>  
  
1.  <span data-ttu-id="c35a3-115">Inicie el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c35a3-115">Start Command Prompt.</span></span>  
  
2.  <span data-ttu-id="c35a3-116">En el símbolo del sistema, cambie el directorio a la ubicación donde DQSInstaller.exe esté disponible.</span><span class="sxs-lookup"><span data-stu-id="c35a3-116">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="c35a3-117">Si instaló la instancia predeterminada de SQL Server, el archivo DQSInstaller.exe estará disponible en C:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="c35a3-117">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
3.  <span data-ttu-id="c35a3-118">En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="c35a3-118">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgradedlls  
    ```  
  
4.  <span data-ttu-id="c35a3-119">Todos los demás pasos son los mismos que los pasos 2 a 6 de la sección [Ejecutar DQSInstaller.exe desde la pantalla Inicio, el menú Inicio o el Explorador de Windows](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) de [Ejecutar DQSInstaller.exe para completar la instalación del servidor de calidad de datos](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="c35a3-119">Rest of the steps are same as steps 2-6 in the [Run DQSInstaller.exe from Start Screen, Start Menu or Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) section in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35a3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c35a3-120">See Also</span></span>  
 <span data-ttu-id="c35a3-121">[Instalar Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="c35a3-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="c35a3-122">Actualizar el esquema de las bases de datos DQS tras instalar la actualización de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c35a3-122">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>](upgrade-dqs-databases-schema-after-installing-sql-server-update.md)  
  
  
