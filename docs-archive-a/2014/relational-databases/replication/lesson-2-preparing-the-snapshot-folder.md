---
title: 'Lección 2: Preparación de la carpeta de instantáneas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749233"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a><span data-ttu-id="a1165-102">Lección 2: Preparar la carpeta de instantáneas</span><span class="sxs-lookup"><span data-stu-id="a1165-102">Lesson 2: Preparing the Snapshot Folder</span></span>
  <span data-ttu-id="a1165-103">En esta lección aprenderá a configurar la carpeta de instantáneas que se utiliza para crear y almacenar la instantánea de publicación.</span><span class="sxs-lookup"><span data-stu-id="a1165-103">In this lesson, you will learn to configure the snapshot folder that is used to create and store the publication snapshot.</span></span>  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a><span data-ttu-id="a1165-104">Para crear un recurso compartido para la carpeta de instantáneas y asignar permisos</span><span class="sxs-lookup"><span data-stu-id="a1165-104">To create a share for the snapshot folder and assign permissions</span></span>  
  
1.  <span data-ttu-id="a1165-105">En el Explorador de Windows, navegue a la carpeta de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1165-105">In Windows Explorer, navigate to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data folder.</span></span> <span data-ttu-id="a1165-106">La ubicación predeterminada es C:\Archivos de programa\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="a1165-106">The default location is C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="a1165-107">Cree una carpeta con el nombre **repldata**.</span><span class="sxs-lookup"><span data-stu-id="a1165-107">Create a new folder named **repldata**.</span></span>  
  
3.  <span data-ttu-id="a1165-108">Haga clic con el botón derecho en esta carpeta y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a1165-108">Right-click this folder and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="a1165-109">En la pestaña **Compartir** del cuadro de diálogo **Propiedades de repldata** , haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="a1165-109">On the **Sharing** tab in the **repldata Properties** dialog box, click **Share**.</span></span>  
  
5.  <span data-ttu-id="a1165-110">En el cuadro de diálogo **Uso compartido de archivos** , haga clic en **Compartir**y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="a1165-110">In the **File Sharing** dialog box, click **Share**, and then click **Done**.</span></span>  
  
6.  <span data-ttu-id="a1165-111">En la pestaña **Seguridad** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a1165-111">On the **Security** tab, click **Edit**.</span></span>  
  
7.  <span data-ttu-id="a1165-112">En el cuadro de diálogo **Permisos** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1165-112">In the **Permissions** dialog box, click **Add.**</span></span> <span data-ttu-id="a1165-113">En el cuadro de texto **Seleccionar usuarios, equipos, cuentas de servicio o grupos** , escriba el nombre de la cuenta agente de instantáneas creada en la lección 1, como \<_Machine_Name> _**\ repl_snapshot**, donde \<*Machine_Name> \* es el nombre del publicador.</span><span class="sxs-lookup"><span data-stu-id="a1165-113">In the **Select User, Computers, Service Account, or Groups** text box, type the name of the Snapshot Agent account created in Lesson 1, as \<_Machine_Name>_**\repl_snapshot**, where \<*Machine_Name>\* is the name of the Publisher.</span></span> <span data-ttu-id="a1165-114">Haga clic en **Comprobar nombres**y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1165-114">Click **Check Names**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a1165-115">Repita el paso anterior para agregar permisos para el agente de distribución, como \<_Machine_Name> _ **\ repl_distribution**y para el agente de mezcla como \<_Machine_Name> _ **\ repl_merge**.</span><span class="sxs-lookup"><span data-stu-id="a1165-115">Repeat the previous step to add permissions for the Distribution Agent, as \<_Machine_Name>_**\repl_distribution**, and for the Merge Agent as \<_Machine_Name>_**\repl_merge**.</span></span>  
  
9. <span data-ttu-id="a1165-116">Compruebe que se admiten los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="a1165-116">Verify the following permissions are allowed:</span></span>  
  
    -   <span data-ttu-id="a1165-117">repl_snapshot - Control total</span><span class="sxs-lookup"><span data-stu-id="a1165-117">repl_snapshot - Full Control</span></span>  
  
    -   <span data-ttu-id="a1165-118">repl_distribution - Lectura</span><span class="sxs-lookup"><span data-stu-id="a1165-118">repl_distribution - Read</span></span>  
  
    -   <span data-ttu-id="a1165-119">repl_merge - Lectura</span><span class="sxs-lookup"><span data-stu-id="a1165-119">repl_merge - Read</span></span>  
  
10. <span data-ttu-id="a1165-120">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Propiedades de repldata** y crear el recurso compartido repldata.</span><span class="sxs-lookup"><span data-stu-id="a1165-120">Click **OK** to close the **repldata Properties** dialog box and create the repldata share.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a1165-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1165-121">Next Steps</span></span>  
 <span data-ttu-id="a1165-122">Ha configurado correctamente el recurso compartido para la carpeta de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="a1165-122">You have successfully configured the share for the snapshot folder.</span></span> <span data-ttu-id="a1165-123">A continuación configurará la distribución.</span><span class="sxs-lookup"><span data-stu-id="a1165-123">Next, you will configure distribution.</span></span> <span data-ttu-id="a1165-124">Consulte [Lección 3: Configurar la distribución](lesson-3-configuring-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="a1165-124">See [Lesson 3: Configuring Distribution](lesson-3-configuring-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1165-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1165-125">See Also</span></span>  
 [<span data-ttu-id="a1165-126">Proteger la carpeta de instantáneas</span><span class="sxs-lookup"><span data-stu-id="a1165-126">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  
