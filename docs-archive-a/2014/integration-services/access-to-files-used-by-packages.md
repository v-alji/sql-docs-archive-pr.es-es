---
title: Acceso a los archivos usados por los paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- packages [Integration Services], security
- configuration files [Integration Services]
- checkpoint files
- Integration Services packages, security
- logs [Integration Services], security
- files [Integration Services], security
- SQL Server Integration Services packages, security
ms.assetid: 2e3ddea9-5289-4289-a70e-11c018f34977
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db9511c91c9f229b7002f5b16cf077910a4ccf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669823"
---
# <a name="access-to-files-used-by-packages"></a><span data-ttu-id="40c4c-102">Acceso a los archivos usados por los paquetes</span><span class="sxs-lookup"><span data-stu-id="40c4c-102">Access to Files Used by Packages</span></span>
  <span data-ttu-id="40c4c-103">El nivel de protección de paquetes no protege los archivos almacenados fuera del paquete.</span><span class="sxs-lookup"><span data-stu-id="40c4c-103">The package protection level does not protect files that are stored outside the package.</span></span> <span data-ttu-id="40c4c-104">Entre los archivos figuran los siguientes:</span><span class="sxs-lookup"><span data-stu-id="40c4c-104">These files include the following:</span></span>  
  
-   <span data-ttu-id="40c4c-105">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="40c4c-105">Configuration files</span></span>  
  
-   <span data-ttu-id="40c4c-106">punto de comprobación, archivos</span><span class="sxs-lookup"><span data-stu-id="40c4c-106">Checkpoint files</span></span>  
  
-   <span data-ttu-id="40c4c-107">Archivos de registro</span><span class="sxs-lookup"><span data-stu-id="40c4c-107">Log files</span></span>  
  
 <span data-ttu-id="40c4c-108">Estos archivos se deben proteger por separado, especialmente si incluyen información confidencial.</span><span class="sxs-lookup"><span data-stu-id="40c4c-108">These files must be protected separately, especially if they include sensitive information.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="40c4c-109">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="40c4c-109">Configuration Files</span></span>  
 <span data-ttu-id="40c4c-110">Si una configuración contiene información confidencial, como información de inicio de sesión o de la contraseña, puede guardar la configuración en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]o usar una lista de control de acceso (ACL) para restringir el acceso a la ubicación o carpeta en la que ha almacenado los archivos y para permitir el acceso solo a determinadas cuentas.</span><span class="sxs-lookup"><span data-stu-id="40c4c-110">If you have sensitive information in a configuration, such as login and password information, you should consider saving the configuration to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], or use an access control list (ACL) to restrict access to the location or folder where you store the files and allow access only to certain accounts.</span></span> <span data-ttu-id="40c4c-111">Por lo general, otorgará acceso a las cuentas a las que permite ejecutar paquetes, y a las cuentas que administran paquetes y que solucionan problemas de paquetes, que pueden incluir la revisión del contenido de archivos de configuración, de punto de comprobación y de registro.</span><span class="sxs-lookup"><span data-stu-id="40c4c-111">Typically, you would grant access to the accounts that you permit to run packages, and to the accounts that manage and troubleshoot packages, which may include reviewing the contents of configuration, checkpoint, and log files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="40c4c-112">proporciona el almacenamiento más seguro dado que ofrece protección en los niveles de servidor y base de datos.</span><span class="sxs-lookup"><span data-stu-id="40c4c-112">provides the more secure storage because it offers protection at the server and database levels.</span></span> <span data-ttu-id="40c4c-113">Para guardar configuraciones en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], utilice el tipo de configuración [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40c4c-113">To save configurations to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type.</span></span> <span data-ttu-id="40c4c-114">Para guardar configuraciones en el sistema de archivos, utilice el tipo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="40c4c-114">To save to the file system, you use the XML configuration type.</span></span>  
  
 <span data-ttu-id="40c4c-115">Para más información, vea [Configuraciones de paquetes](../../2014/integration-services/package-configurations.md), [Crear configuraciones de paquetes](../../2014/integration-services/create-package-configurations.md)y [Consideraciones de seguridad para una instalación de SQL Server](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="40c4c-115">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md), [Create Package Configurations](../../2014/integration-services/create-package-configurations.md), and [Security Considerations for a SQL Server Installation](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span></span>  
  
## <a name="checkpoint-files"></a><span data-ttu-id="40c4c-116">punto de comprobación, archivos</span><span class="sxs-lookup"><span data-stu-id="40c4c-116">Checkpoint Files</span></span>  
 <span data-ttu-id="40c4c-117">De igual modo, si el archivo de punto de comprobación que utiliza el paquete incluye información confidencial, debe utilizar una lista de control de acceso (ACL) para asegurar la ubicación o carpeta en la que ha almacenado el archivo.</span><span class="sxs-lookup"><span data-stu-id="40c4c-117">Similarly, if the checkpoint file that the package uses includes sensitive information, you should use an access control list (ACL) to secure the location or folder where you store the file.</span></span> <span data-ttu-id="40c4c-118">Los archivos de punto de comprobación guardan la información de estado actual acerca del progreso del paquete y los valores actuales de las variables.</span><span class="sxs-lookup"><span data-stu-id="40c4c-118">Checkpoint files save current state information on the progress of the package as well as the current values of variables.</span></span> <span data-ttu-id="40c4c-119">Por ejemplo, el paquete puede incluir una variable personalizada que contiene un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="40c4c-119">For example, the package may include a custom variable that contains a telephone number.</span></span> <span data-ttu-id="40c4c-120">Para obtener más información, vea [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span><span class="sxs-lookup"><span data-stu-id="40c4c-120">For more information, see [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span></span>  
  
## <a name="log-files"></a><span data-ttu-id="40c4c-121">Archivos de registro</span><span class="sxs-lookup"><span data-stu-id="40c4c-121">Log Files</span></span>  
 <span data-ttu-id="40c4c-122">También es necesario proteger las entradas del registro escritas en el sistema de archivos mediante una lista de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="40c4c-122">Log entries that are written to the file system should also be secured using an access control list (ACL).</span></span> <span data-ttu-id="40c4c-123">Las entradas del registro pueden almacenarse también en tablas de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y protegerse con la seguridad de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40c4c-123">Log entries can also be stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables and protected by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security.</span></span> <span data-ttu-id="40c4c-124">Las entradas del registro pueden incluir información confidencial. Por ejemplo, si el paquete contiene una tarea Ejecutar SQL que crea una instrucción SQL que hace referencia a un número de teléfono, la entrada del registro de la instrucción SQL incluye el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="40c4c-124">Log entries may include sensitive information, For example, if the package contains an Execute SQL task that constructs an SQL statement that refers to a telephone number, the log entry for the SQL statement includes the telephone number.</span></span> <span data-ttu-id="40c4c-125">La instrucción SQL puede revelar información privada acerca de los nombres de tablas y columnas de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="40c4c-125">The SQL statement may also reveal private information about table and column names in databases.</span></span> <span data-ttu-id="40c4c-126">Para obtener más información, vea [Registro de Integration Services &#40;SSIS&#41;](performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="40c4c-126">For more information, see [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md).</span></span>  
  
  
