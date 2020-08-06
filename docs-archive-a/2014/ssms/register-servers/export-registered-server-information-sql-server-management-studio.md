---
title: Exportar información de servidores registrados
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 03092de2d722e8f8b807dbb3d23c4b4e2b91f6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748463"
---
# <a name="export-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="67d6d-102">Exportar información de servidores registrados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="67d6d-102">Export Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="67d6d-103">En este tema se describe cómo guardar y exportar información de servidores registrados en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]para distribuirla a otros empleados o servidores.</span><span class="sxs-lookup"><span data-stu-id="67d6d-103">This topic describes how to save and export registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]and distribute it to other employees or servers.</span></span> <span data-ttu-id="67d6d-104">Puede utilizar esta característica de exportación para crear una interfaz de usuario coherente en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="67d6d-104">You can use this export feature to present a consistent user interface on multiple computers.</span></span>  
  
 <span data-ttu-id="67d6d-105">La exportación y posterior importación de archivos de servidores registrados permite configurar fácilmente varios equipos con los mismos servidores en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="67d6d-105">Exporting and then importing Registered Server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="67d6d-106">Esto resulta útil cuando se administra un gran número de servidores desde equipos en varias ubicaciones, o cuando se desea configurar un usuario menos experto con una configuración de conexión básica.</span><span class="sxs-lookup"><span data-stu-id="67d6d-106">This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67d6d-107">Los registros de servidor que usan la autenticación de SQL Server almacenan las contraseñas por usuario.</span><span class="sxs-lookup"><span data-stu-id="67d6d-107">Server registrations that use SQL Server Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="67d6d-108">Después de exportar e importar los registros de servidor, los usuarios deben escribir la contraseña para cada servidor la primera vez que se conectan, y almacenar así las contraseñas en las listas de los servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="67d6d-108">After exporting and importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="67d6d-109">Esto no es necesario en los servidores registrados mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="67d6d-109">This is not necessary for servers registered using Windows Authentication.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a><span data-ttu-id="67d6d-110">Para exportar información del servidor registrado</span><span class="sxs-lookup"><span data-stu-id="67d6d-110">To export registered server information</span></span>  
  
1.  <span data-ttu-id="67d6d-111">En Servidores registrados, haga clic con el botón derecho en un grupo de servidores y, luego, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="67d6d-111">In Registered Servers, right-click a server group, and then click **Export**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67d6d-112">Se puede exportar un solo servidor, todo el árbol de servidores registrados o un subconjunto del árbol.</span><span class="sxs-lookup"><span data-stu-id="67d6d-112">You can export an individual server, all of the registered server tree, or a subset of the registered server tree.</span></span>  
  
2.  <span data-ttu-id="67d6d-113">En el cuadro de diálogo **Exportar servidores registrados** , realice las selecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="67d6d-113">In the **Export Registered Servers** dialog box, make the following selections.</span></span>  
  
     <span data-ttu-id="67d6d-114">**Grupo del servidor**</span><span class="sxs-lookup"><span data-stu-id="67d6d-114">**Server group**</span></span>  
     <span data-ttu-id="67d6d-115">Especifique el grupo de servidores que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="67d6d-115">Specify the server group which will be exported.</span></span> <span data-ttu-id="67d6d-116">Puede exportar todos los servidores registrados, los servidores registrados de un grupo de servidores determinado o un solo servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="67d6d-116">Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="67d6d-117">La función de exportación es recursiva; por ejemplo, si el grupo de servidores A contiene el grupo de servidores B y éste contiene los grupos C y D, la exportación del grupo A exporta todas las entradas de A, B, C y D.</span><span class="sxs-lookup"><span data-stu-id="67d6d-117">The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="67d6d-118">El grupo de servidores muestra solo los grupos del actual árbol de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="67d6d-118">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="67d6d-119">**Archivo de exportación**</span><span class="sxs-lookup"><span data-stu-id="67d6d-119">**Export file**</span></span>  
     <span data-ttu-id="67d6d-120">Escriba el nombre del archivo de exportación en el cuadro de texto o use el botón Examinar ( **...** ) para buscar un archivo de exportación en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="67d6d-120">Type the name of the export file in the text box or use the Browse button (**...**) to locate an export file on the client computer.</span></span> <span data-ttu-id="67d6d-121">Si selecciona un archivo existente, la información del servidor registrado se anexa al archivo.</span><span class="sxs-lookup"><span data-stu-id="67d6d-121">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="67d6d-122">Utilice la extensión .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="67d6d-122">Use the .regsrvr extension.</span></span> <span data-ttu-id="67d6d-123">Si desea que la información del servidor registrado esté disponible para otros usuarios u otro equipo, puede guardar el archivo en la red.</span><span class="sxs-lookup"><span data-stu-id="67d6d-123">If you want your registered server information to be available to other users or another computer, you can save the file on the network.</span></span> <span data-ttu-id="67d6d-124">De este modo, otros usuarios podrán obtener acceso al archivo e importar parte o la totalidad de la información del servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="67d6d-124">Other users can access the file and import part or all of the registered server information.</span></span> <span data-ttu-id="67d6d-125">Si selecciona un archivo existente como archivo de exportación, el contenido del archivo se sobrescribirá con la información del servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="67d6d-125">If you select an existing file as your export file, the contents of the file are overwritten with the server registration information.</span></span>  
  
     <span data-ttu-id="67d6d-126">**No incluir nombres de usuario ni contraseñas en el archivo de exportación**</span><span class="sxs-lookup"><span data-stu-id="67d6d-126">**Do not include user names and passwords in the export file**</span></span>  
     <span data-ttu-id="67d6d-127">Excluye los nombres de usuario en la exportación del archivo.</span><span class="sxs-lookup"><span data-stu-id="67d6d-127">Exclude user names when exporting the file.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="67d6d-128">Los archivos de exportación están cifrados; sin embargo, si se incluyen nombres de usuario y contraseñas para la autenticación de SQL Server, el acceso al archivo debe controlarse cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="67d6d-128">Although the export files are encrypted, if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled.</span></span> <span data-ttu-id="67d6d-129">De manera predeterminada, los nombres de usuario y las contraseñas se excluyen del archivo de exportación.</span><span class="sxs-lookup"><span data-stu-id="67d6d-129">User names and passwords are therefore excluded from the export file by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d6d-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67d6d-130">See Also</span></span>  
 <span data-ttu-id="67d6d-131">[Importar información de servidores registrados &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [crear un nuevo servidor registrado &#40;SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="67d6d-131">[Import Registered Server Information &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span></span>  
  
  
