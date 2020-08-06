---
title: Habilitar un publicador remoto en un distribuidor (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- remote Distributors [SQL Server replication]
- Publishers [SQL Server replication]
ms.assetid: 6f8e2831-5c45-4e39-8e51-d37e2813cf3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 06c85924731b79e8b3c79cfbcc354b5bedf69b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663372"
---
# <a name="enable-a-remote-publisher-at-a-distributor-sql-server-management-studio"></a><span data-ttu-id="67636-102">Habilitar un publicador remoto en un distribuidor (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="67636-102">Enable a Remote Publisher at a Distributor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="67636-103">Habilite un publicador para utilizar un distribuidor remoto en la página **Publicadores** .</span><span class="sxs-lookup"><span data-stu-id="67636-103">Enable a Publisher to use a remote Distributor on the **Publishers** page.</span></span> <span data-ttu-id="67636-104">Esta página está disponible en el Asistente para configurar la distribución y en el cuadro de diálogo **Propiedades del distribuidor: \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="67636-104">This page is available in the Configure Distribution Wizard and the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="67636-105">Para obtener más información sobre el uso del asistente y el acceso al cuadro de diálogo, consulte [Configurar la publicación y la distribución](configure-publishing-and-distribution.md) y [Ver y modificar propiedades del distribuidor y el publicador](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="67636-105">For more information about using the wizard and accessing the dialog box, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-enable-a-publisher-in-the-configure-distribution-wizard"></a><span data-ttu-id="67636-106">Para habilitar un publicador en el Asistente para configurar la distribución</span><span class="sxs-lookup"><span data-stu-id="67636-106">To enable a Publisher in the Configure Distribution Wizard</span></span>  
  
1.  <span data-ttu-id="67636-107">En la página **Publicadores** del Asistente para configurar la distribución, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67636-107">On the **Publishers** page of the Configure Distribution Wizard, click **Add**.</span></span>  
  
2.  <span data-ttu-id="67636-108">Haga clic en **Agregar publicador de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="67636-108">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="67636-109">Para obtener información acerca de cómo habilitar un publicador de Oracle para utilizar un distribuidor, vea [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="67636-109">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="67636-110">En el cuadro de diálogo **Conectar al servidor** , especifique la información de conexión con el publicador que utilizará el distribuidor remoto y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="67636-110">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="67636-111">En la página **Contraseña del distribuidor** , en los cuadros de texto **Contraseña** y **Confirmar contraseña** , especifique una contraseña segura para la cuenta **distributor_admin** , que la replicación utiliza para conectar del publicador al distribuidor y realizar las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="67636-111">On the **Distributor Password** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="67636-112">Para ver y modificar la configuración de un publicador, haga clic en el botón de propiedades ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="67636-112">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-enable-a-publisher-in-the-distributor-properties-dialog-box"></a><span data-ttu-id="67636-113">Para habilitar un publicador en el cuadro de diálogo Propiedades del distribuidor</span><span class="sxs-lookup"><span data-stu-id="67636-113">To enable a Publisher in the Distributor Properties dialog box</span></span>  
  
1.  <span data-ttu-id="67636-114">En la página **Publicadores** del cuadro de diálogo **Propiedades del distribuidor: \<Distributor>** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67636-114">On the **Publishers** page of the **Distributor Properties - \<Distributor>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="67636-115">Haga clic en **Agregar publicador de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="67636-115">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="67636-116">Para obtener información acerca de cómo habilitar un publicador de Oracle para utilizar un distribuidor, vea [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="67636-116">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="67636-117">En el cuadro de diálogo **Conectar al servidor** , especifique la información de conexión con el publicador que utilizará el distribuidor remoto y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="67636-117">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="67636-118">En la página **Publicadores** , en los cuadros de texto **Contraseña** y **Confirmar contraseña** , especifique una contraseña segura para la cuenta **distributor_admin** , que la replicación utiliza para conectar del publicador al distribuidor y realizar las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="67636-118">On the **Publishers** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="67636-119">Para ver y modificar la configuración de un publicador, haga clic en el botón de propiedades ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="67636-119">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67636-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67636-120">See Also</span></span>  
 <span data-ttu-id="67636-121">[Configurar la publicación y la distribución](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="67636-121">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="67636-122">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="67636-122">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="67636-123">Proteger el distribuidor</span><span class="sxs-lookup"><span data-stu-id="67636-123">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
