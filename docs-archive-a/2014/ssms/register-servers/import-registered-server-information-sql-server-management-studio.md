---
title: Importar información de servidores registrados
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.importregisteredservers.f1
helpviewer_keywords:
- transferring registered server information
- Registered Servers [SQL Server], importing
- importing registered server information
ms.assetid: cc497a14-1360-4887-b70c-002f042823b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f2eddb3b83f73253e977316767f2b930bc8ab9ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748464"
---
# <a name="import-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="b7cb8-102">Importar información de servidores registrados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b7cb8-102">Import Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b7cb8-103">En este tema se describe cómo importar información guardada de servidores registrados en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7cb8-103">This topic describes how to import saved registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b7cb8-104">La exportación e importación de archivos de un servidor registrado permite configurar fácilmente varios equipos con los mismos servidores en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-104">Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="b7cb8-105">Esto resulta útil cuando se administra un gran número de servidores desde equipos en distintas ubicaciones, o cuando desea establecer la configuración de conexión básica para un usuario menos experimentado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-105">This is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less-experienced user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7cb8-106">No puede importar información de servidores registrados en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] desde versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7cb8-106">You cannot import registered server information into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-import-registered-server-information"></a><span data-ttu-id="b7cb8-107">Para importar información de servidores registrados</span><span class="sxs-lookup"><span data-stu-id="b7cb8-107">To import registered server information</span></span>  
  
1.  <span data-ttu-id="b7cb8-108">En Servidores registrados, haga clic en el tipo de servidor en la barra de herramientas Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-108">In Registered Servers, click the server type on the Registered Servers toolbar.</span></span> <span data-ttu-id="b7cb8-109">El tipo de servidor debe ser el mismo que el tipo de archivo de exportación de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-109">The server type must be the same as the registered server export file type.</span></span> <span data-ttu-id="b7cb8-110">Por ejemplo, si ha exportado la información de un servidor registrado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , debe hacer clic en **SQL Server** en la barra de herramientas Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-110">For example, if you have exported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registered server information, you must click **SQL Server** on the Registered Servers toolbar.</span></span>  
  
2.  <span data-ttu-id="b7cb8-111">Haga clic con el botón derecho en un grupo de servidores y seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-111">Right-click a server group, and select **Import**.</span></span>  
  
3.  <span data-ttu-id="b7cb8-112">En el cuadro de diálogo **Importar servidores registrados** , seleccione el archivo de servidores registrados que desea importar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-112">In the **Import Registered Servers** dialog box, select the registered servers file to import, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b7cb8-113">**Importar archivo**</span><span class="sxs-lookup"><span data-stu-id="b7cb8-113">**Import file**</span></span>  
     <span data-ttu-id="b7cb8-114">Escriba el nombre del archivo de importación en el cuadro de texto o haga clic en el botón Explorar ( **...** ) para localizar el archivo en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-114">Type the name of the import file in the text box, or click the Browse button (**...**) to locate the import file on the client computer.</span></span> <span data-ttu-id="b7cb8-115">Si selecciona un archivo existente, la información del servidor registrado se anexa al archivo.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-115">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="b7cb8-116">El archivo de importación solo puede ser un archivo de servidor registrado exportado previamente.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-116">The import file can only be a previously exported registered server file.</span></span> <span data-ttu-id="b7cb8-117">Los archivos de servidor registrado tienen una extensión .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-117">Registered server files have a .regsrvr extension.</span></span>  
  
     <span data-ttu-id="b7cb8-118">**Seleccionar el grupo de servidores de destino de la importación**</span><span class="sxs-lookup"><span data-stu-id="b7cb8-118">**Select the server group to import to**</span></span>  
     <span data-ttu-id="b7cb8-119">Seleccione el nodo raíz o un grupo de servidores específico al que se importarán las entradas del servidor registrado del archivo.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-119">Select the root node or a particular server group to which the registered server entries in the file will be imported.</span></span> <span data-ttu-id="b7cb8-120">Puede importar al archivo de exportación todos los servidores registrados, los servidores registrados de un grupo de servidores específico o un único servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-120">You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="b7cb8-121">La funcionalidad de importación es recursiva; por ejemplo, si un grupo de servidores A contiene un grupo de servidores B, y un grupo de servidores B contiene grupos de servidores C y D; la importación del grupo de servidores A exporta todas las entradas de A, B, C y D.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-121">The import functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, importing server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="b7cb8-122">El grupo de servidores muestra solo los grupos del actual árbol de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-122">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="b7cb8-123">Si selecciona un grupo de servidores o un servidor para la importación, un mensaje confirmará que desea sobrescribir el grupo de servidores o el servidor existente.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-123">If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.</span></span>  
  
 <span data-ttu-id="b7cb8-124">Los registros de servidor que usan la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] almacenan las contraseñas por usuario.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-124">Server registrations that use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="b7cb8-125">Después de importar los registros de servidor, los usuarios deben escribir la contraseña para cada servidor la primera vez que se conectan, y almacenar así las contraseñas en las listas de los servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-125">After importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="b7cb8-126">Esto no es necesario en los servidores registrados mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-126">This is not necessary for servers registered through Windows Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cb8-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7cb8-127">See Also</span></span>  
 <span data-ttu-id="b7cb8-128">[Cambiar el registro de un servidor &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [exportar información de servidores registrados &#40;SQL Server Management Studio](export-registered-server-information-sql-server-management-studio.md)&#41; </span><span class="sxs-lookup"><span data-stu-id="b7cb8-128">[Change a Server's Registration &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Export Registered Server Information &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="b7cb8-129">Crear un servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b7cb8-129">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)  
  
  
