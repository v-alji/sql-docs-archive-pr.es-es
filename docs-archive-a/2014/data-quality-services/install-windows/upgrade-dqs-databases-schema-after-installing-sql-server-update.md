---
title: Actualizar el esquema de las bases de datos DQS después de instalar la actualización de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: c8f3fbae-02c4-464d-a35c-7108f48c58cb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 80a1714ea250cf7cf5d34bc9d208a42a64284308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673913"
---
# <a name="upgrade-dqs-databases-schema-after-installing-sql-server-update"></a><span data-ttu-id="0e5f4-102">Actualizar el esquema de las bases de datos DQS tras instalar la actualización de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e5f4-102">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>
  <span data-ttu-id="0e5f4-103">Tras instalar una actualización de SQL Server (revisión o actualización acumulativa) en una instancia de DQS configurada previamente, puede que tenga que actualizar el esquema de bases de datos DQS ejecutando el archivo DQSInstaller.exe con el parámetro de la línea de comandos **upgrade** .</span><span class="sxs-lookup"><span data-stu-id="0e5f4-103">After you have installed a SQL Server update (patch, hotfix, or cumulative update) on a previously configured DQS instance, you might have to upgrade the DQS databases schema by running the DQSInstaller.exe file with the **upgrade** command line parameter.</span></span> <span data-ttu-id="0e5f4-104">De lo contrario, podría recibir un mensaje de error similar al siguiente al intentar conectarse a Data Quality Server con su Data Quality Client:</span><span class="sxs-lookup"><span data-stu-id="0e5f4-104">Otherwise, you might receive the following error while trying to connect to Data Quality Server using your Data Quality Client:</span></span>  
  
```  
An error occurred in the Microsoft .NET Framework while trying to load assembly id 65581.  
```  
  
 <span data-ttu-id="0e5f4-105">La actualización del esquema de bases de datos DQS no afecta a los datos actuales de las bases de datos DQS (bases de conocimiento, proyectos de calidad de datos y resultados exportados en la base de datos DQS_STAGING_DATA).</span><span class="sxs-lookup"><span data-stu-id="0e5f4-105">Upgrading DQS databases schema does not impact your existing data in the DQS databases (knowledge bases, data quality projects, and exported results in the DQS_STAGING_DATA database).</span></span> <span data-ttu-id="0e5f4-106">Sin embargo, debe hacer una copia de seguridad de las bases de datos DQS antes de actualizar el esquema de las bases de datos DQS para impedir la pérdida accidental de datos durante la actualización del esquema.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-106">However, you must back up your DQS databases before upgrading DQS databases schema to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="0e5f4-107">Para obtener información sobre la copia de seguridad de bases de datos de DQS, vea [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0e5f4-107">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e5f4-108">La mayor parte de las actualizaciones de SQL Server requerirán una actualización del esquema de bases de datos DQS.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-108">Most of the SQL Server updates will require an upgrade to the DQS databases schema.</span></span> <span data-ttu-id="0e5f4-109">Para obtener información acerca de las actualizaciones de SQL Server que requerirán una actualización al esquema de bases de datos DQS, vea el gráfico del paso 1.A en [Actualizar DQS: instalar actualizaciones acumulativas o revisiones en Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span><span class="sxs-lookup"><span data-stu-id="0e5f4-109">For information about the SQL Server updates that will require an upgrade to the DQS databases schema, see the chart in step 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0e5f4-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0e5f4-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="0e5f4-111">Debe haber iniciado sesión como miembro del grupo Administradores en el equipo con [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e5f4-111">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="0e5f4-112">La cuenta de usuario de Windows debe ser miembro del rol fijo de servidor sysadmin en la instancia de SQL Server donde está instalado [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e5f4-112">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-dqs-databases-schema"></a><span data-ttu-id="0e5f4-113">Para actualizar el esquema de bases de datos DQS</span><span class="sxs-lookup"><span data-stu-id="0e5f4-113">To upgrade DQS databases schema</span></span>  
  
1.  <span data-ttu-id="0e5f4-114">(Recomendado) Haga copia de seguridad de sus bases de datos DQS antes de continuar con la actualización del esquema.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-114">(Recommended) Back up your DQS databases before you proceed with the schema upgrade.</span></span> <span data-ttu-id="0e5f4-115">Para obtener información sobre la copia de seguridad de bases de datos de DQS, vea [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0e5f4-115">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="0e5f4-116">Inicie el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-116">Start Command Prompt.</span></span>  
  
3.  <span data-ttu-id="0e5f4-117">En el símbolo del sistema, cambie el directorio a la ubicación donde DQSInstaller.exe esté disponible.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-117">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="0e5f4-118">Si instaló la instancia predeterminada de SQL Server, el archivo DQSInstaller.exe estará disponible en C:\Archivos de programa\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="0e5f4-118">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
4.  <span data-ttu-id="0e5f4-119">En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="0e5f4-119">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgrade  
    ```  
  
5.  <span data-ttu-id="0e5f4-120">El instalador le pregunta si desea realizar la copia de seguridad de las bases de datos DQS antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-120">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="0e5f4-121">Si aún no la ha hecho, escriba `Y` o `Yes` y presione ENTRAR para continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-121">If you have already backed up your DQS databases, type `Y` or `Yes` and press ENTER to continue with the upgrade.</span></span>  
  
6.  <span data-ttu-id="0e5f4-122">Se muestra un mensaje para indicar que la actualización del esquema de las bases de datos DQS se realizó.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-122">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0e5f4-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0e5f4-123">Next Steps</span></span>  
 <span data-ttu-id="0e5f4-124">Inicie sesión en el servidor Data Quality Server actualizado desde una aplicación Data Quality Client.</span><span class="sxs-lookup"><span data-stu-id="0e5f4-124">Log on to the upgraded Data Quality Server from a Data Quality Client application.</span></span>  
  
 <span data-ttu-id="0e5f4-125">Para obtener más acerca de cómo actualizar el esquema de bases de datos DQS tras instalar las actualizaciones de SQL Server y sobre los pasos de solución de problemas asociados, vea [Actualizar DQS: instalar actualizaciones acumulativas o revisiones en Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span><span class="sxs-lookup"><span data-stu-id="0e5f4-125">For more information about upgrading DQS databases schema after installing SQL Server updates and associated troubleshooting steps, see [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5f4-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e5f4-126">See Also</span></span>  
 <span data-ttu-id="0e5f4-127">[Instalar Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="0e5f4-127">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="0e5f4-128">Actualizar ensamblados de SQLCLR después de actualizar .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0e5f4-128">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>](upgrade-sqlclr-assemblies-after-net-framework-update.md)  
  
  
