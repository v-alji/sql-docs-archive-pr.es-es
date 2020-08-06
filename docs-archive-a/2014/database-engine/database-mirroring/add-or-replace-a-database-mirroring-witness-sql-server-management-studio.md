---
title: Agregar o reemplazar un testigo de creación de reflejo de la base de datos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670581"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a><span data-ttu-id="bb6c7-102">Agregar o reemplazar un testigo de creación de reflejo de la base de datos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bb6c7-102">Add or Replace a Database Mirroring Witness (SQL Server Management Studio)</span></span>
  <span data-ttu-id="bb6c7-103">Si los extremos de la creación de reflejo de la base de datos usan la Autenticación de Windows, puede usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para agregar o reemplazar un testigo.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-103">If the database mirroring endpoints use Windows Authentication,, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add or replace a witness.</span></span> <span data-ttu-id="bb6c7-104">Cuando se agrega un testigo en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , se cambia también el modo de operación al modo de alta seguridad con conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-104">Adding a witness in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] also changes the operating mode to high-safety mode with automatic failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb6c7-105">Es muy recomendable que el testigo se encuentre en otro equipo de alguno de los asociados.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-105">We strongly recommend that the witness reside on a separate computer from either of the partners.</span></span> <span data-ttu-id="bb6c7-106">La cuenta de servicio que usa el testigo debe estar en el mismo dominio que las cuentas de servicio que usan las instancias del servidor principal y del servidor reflejado, o bien debe estar en un dominio de confianza.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-106">The service account used by the witness must be in the same domain as the service accounts used by the principal and mirror server instances, or it must be in a trusted domain.</span></span>  
  
### <a name="to-add-or-replace-a-witness"></a><span data-ttu-id="bb6c7-107">Para agregar o reemplazar un testigo</span><span class="sxs-lookup"><span data-stu-id="bb6c7-107">To Add or Replace a Witness</span></span>  
  
1.  <span data-ttu-id="bb6c7-108">Después de conectarse a la instancia del servidor principal, en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol del servidor.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-108">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="bb6c7-109">Expanda **Bases de datos**y seleccione la base de datos principal de la sesión en la que desee agregar o reemplazar un testigo.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-109">Expand **Databases**, and select the principal database of the session to which you are adding or replacing a witness.</span></span>  
  
3.  <span data-ttu-id="bb6c7-110">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Reflejado**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-110">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="bb6c7-111">Así se abre la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="bb6c7-111">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="bb6c7-112">Haga clic en **Configurar seguridad**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-112">Click **Configure Security**.</span></span>  
  
5.  <span data-ttu-id="bb6c7-113">Cuando aparezca la pantalla de bienvenida del **Asistente para la configuración de seguridad de la creación de reflejo de bases de datos** , seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-113">If the **Configure Database Mirroring Security Wizard** welcome screen appears, click **Next**.</span></span>  
  
6.  <span data-ttu-id="bb6c7-114">En el cuadro de diálogo **Incluir servidor testigo** , haga clic en **Sí**y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-114">In the **Include Witness Server** dialog box, click **Yes**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="bb6c7-115">En el cuadro de diálogo **Elegir los servidores para configurar** , se marcará automáticamente la casilla **Instancia del servidor testigo** .</span><span class="sxs-lookup"><span data-stu-id="bb6c7-115">In the **Choose Servers to Configure** dialog box, the **Witness server instance** check box is automatically checked.</span></span> <span data-ttu-id="bb6c7-116">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-116">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="bb6c7-117">En el cuadro de diálogo **Instancia del servidor principal** , conserve las opciones existentes de puerto y extremos.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-117">On the **Principal Server Instance** dialog box, keep the existing port and endpoint.</span></span> <span data-ttu-id="bb6c7-118">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="bb6c7-119">En el cuadro de diálogo **Instancia del servidor testigo** , haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-119">On the **Witness Server Instance** dialog box, click **Connect**.</span></span>  
  
10. <span data-ttu-id="bb6c7-120">En el cuadro de diálogo **Conectar al servidor** , especifique la instancia del servidor testigo en el campo **Nombre del servidor** y use la Autenticación de Windows (opción predeterminada).</span><span class="sxs-lookup"><span data-stu-id="bb6c7-120">In the **Connect to Server** dialog box, specify the witness server instance in the **Server name** field, and use Windows Authentication (the default).</span></span> <span data-ttu-id="bb6c7-121">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-121">Click **Connect**.</span></span>  
  
11. <span data-ttu-id="bb6c7-122">Una vez que se haya establecido una conexión, en el cuadro de diálogo **Instancia del servidor testigo** se mostrará el puerto de escucha y el extremo de la creación de reflejo de la base de datos de la instancia del servidor testigo.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-122">Once a connection is established, the listener port and database mirroring endpoint of the witness server instance are displayed on the **Witness Server Instance** dialog box.</span></span> <span data-ttu-id="bb6c7-123">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-123">Click **Next**.</span></span>  
  
12. <span data-ttu-id="bb6c7-124">El cuadro de diálogo **Cuentas de servicio** contiene campos para las cuentas de servicio de dominio de las instancias del servidor reflejado, principal y testigo.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-124">The **Service Accounts** dialog box contains fields for the domain service accounts of the principal, mirror, and witness server instances.</span></span>  
  
    -   <span data-ttu-id="bb6c7-125">Si todas las instancias del servidor utilizan la misma cuenta de servicio, deje los campos en blanco.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-125">If the server instances all use the same service account, leave the fields blank.</span></span>  
  
    -   <span data-ttu-id="bb6c7-126">Si la instancia del servidor testigo usa una cuenta de servicio diferente de las de los asociados, llene los campos **Principal**, **Reflejado**y **Testigo** con el nombre de la cuenta:</span><span class="sxs-lookup"><span data-stu-id="bb6c7-126">If the witness server instance uses a different service account from either of the partners, fill in the **Principal**, **Mirror**, and **Witness** fields with the account name:</span></span>  
  
         <span data-ttu-id="bb6c7-127">*DOMAINNAME* **\\** *nombre de usuario*</span><span class="sxs-lookup"><span data-stu-id="bb6c7-127">*DOMAINNAME* **\\** *username*</span></span>  
  
         <span data-ttu-id="bb6c7-128">El nombre de dominio debe estar en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-128">The domain name must be in upper case.</span></span>  
  
     <span data-ttu-id="bb6c7-129">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-129">Click **Next**.</span></span>  
  
13. <span data-ttu-id="bb6c7-130">Si lo desea, en la pantalla de resumen **Finalización del asistente** , compruebe la configuración del testigo y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-130">On the **Complete the Wizard** summary screen, optionally, verify the witness configuration, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="bb6c7-131">Cuando finalice, el asistente volverá al cuadro de diálogo **Propiedades de la base de datos** , donde en el campo **Testigo** se mostrará la dirección de red del servidor del testigo.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-131">On finishing, the wizard returns you to the **Database Properties** dialog box where the server network address of the witness now appears in **Witness** field.</span></span> <span data-ttu-id="bb6c7-132">Además, se seleccionará automáticamente **Modo de alta seguridad con conmutación por error automática (sincrónica)** , que es necesario con un testigo.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-132">Also, **High-safety mode with automatic failover (synchronous)**, which is required with a witness, is automatically selected.</span></span>  
  
     <span data-ttu-id="bb6c7-133">Para habilitar el testigo y cambiar la sesión al modo de alta seguridad con conmutación por error automática, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb6c7-133">To enable the witness and change the session to high-safety mode with automatic failover, Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6c7-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb6c7-134">See Also</span></span>  
 <span data-ttu-id="bb6c7-135">[Testigo de creación de reflejo de la base de datos](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="bb6c7-135">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="bb6c7-136">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bb6c7-136">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="bb6c7-137">[Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="bb6c7-137">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="bb6c7-138">[Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="bb6c7-138">[Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span></span>  
 [<span data-ttu-id="bb6c7-139">Testigo de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="bb6c7-139">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
