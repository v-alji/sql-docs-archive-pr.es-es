---
title: Publicador de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.selectoraclepublisher.f1
ms.assetid: 019b7c49-dcca-445d-8969-5982a8ccbc1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: db52b93b3d260ff58a151e7238bbbe065bc47bc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662816"
---
# <a name="oracle-publisher"></a><span data-ttu-id="bd1f1-102">Publicador de Oracle</span><span class="sxs-lookup"><span data-stu-id="bd1f1-102">Oracle Publisher</span></span>
  <span data-ttu-id="bd1f1-103">A partir de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite publicar datos de una base de datos de Oracle mediante replicación transaccional y de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-103">Beginning with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to publish data from an Oracle database using snapshot and transactional replication.</span></span> <span data-ttu-id="bd1f1-104">Para obtener más información, vea [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md) (Información general de la publicación de Oracle).</span><span class="sxs-lookup"><span data-stu-id="bd1f1-104">For more information, see [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="bd1f1-105">El publicador de Oracle debe utilizar un distribuidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] remoto. Este asistente se debe ejecutar en ese servidor después de que se haya instalado y probado el software de red de Oracle necesario.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-105">The Oracle Publisher must use a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor; this wizard must be run on that server after the necessary Oracle networking software has been installed and tested.</span></span> <span data-ttu-id="bd1f1-106">Para obtener más información, vea [Configurar un publicador de Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f1-106">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd1f1-107">Si otro administrador configuró la base de datos de Oracle como publicador, después de hacer clic en **Siguiente** , se le solicitará que escriba la contraseña del inicio de sesión de replicación que se utiliza para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-107">If another administrator configured the Oracle database as a Publisher, after clicking **Next** you will be prompted to enter the password for the replication login used to connect to the Oracle database.</span></span> <span data-ttu-id="bd1f1-108">A continuación,[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creará una asignación entre su inicio de sesión y la conexión del servidor vinculado a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will then create a mapping between your login and the linked server connection to the Oracle database.</span></span> <span data-ttu-id="bd1f1-109">No no será necesario que escriba una contraseña cada vez que vuelva a conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-109">You will not be required to enter a password for subsequent connections to the Oracle database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bd1f1-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="bd1f1-110">Options</span></span>  
 <span data-ttu-id="bd1f1-111">**Publicadores de Oracle**</span><span class="sxs-lookup"><span data-stu-id="bd1f1-111">**Oracle Publishers**</span></span>  
 <span data-ttu-id="bd1f1-112">Seleccione un publicador de Oracle de la lista.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-112">Select an Oracle Publisher from the list.</span></span> <span data-ttu-id="bd1f1-113">Esta lista contiene los publicadores de Oracle que se configuraron previamente para utilizar el servidor en el que se está ejecutando el asistente como su distribuidor.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-113">This list contains Oracle Publishers that have previously been configured to use the server against which the wizard is running as their Distributor.</span></span> <span data-ttu-id="bd1f1-114">Si la lista está vacía o si el publicador de Oracle que desea utilizar no figura en la lista, haga clic en **Agregar publicador de Oracle**.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-114">If the list is empty, or the Oracle Publisher you want to use is not in the list, click **Add Oracle Publisher**.</span></span>  
  
 <span data-ttu-id="bd1f1-115">**Agregar publicador de Oracle**</span><span class="sxs-lookup"><span data-stu-id="bd1f1-115">**Add Oracle Publisher**</span></span>  
 <span data-ttu-id="bd1f1-116">Haga clic en esta opción para abrir el cuadro de diálogo **Propiedades del distribuidor** .</span><span class="sxs-lookup"><span data-stu-id="bd1f1-116">Click to launch the **Distributor Properties** dialog box.</span></span> <span data-ttu-id="bd1f1-117">En este cuadro de diálogo, haga clic en **Agregar**y, a continuación, en **Agregar publicador de Oracle**.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-117">In this dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span> <span data-ttu-id="bd1f1-118">En el cuadro de diálogo **Conectar al servidor** , especifique el nombre del servidor de Oracle y el inicio de sesión y la contraseña correspondientes al esquema de usuario administrativo de replicación.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-118">In the **Connect to Server** dialog box, specify the Oracle server name, and the login and password for the replication administrative user schema.</span></span> <span data-ttu-id="bd1f1-119">Para obtener más información, vea [Conectar al servidor &#40;motor de base de datos&#41;](connect-to-server-oracle-login.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f1-119">For more information, see [Connect to Server &#40;Oracle&#41;, Login](connect-to-server-oracle-login.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd1f1-120">Si el servidor en el que se ejecuta el asistente aún no ha sido configurado como distribuidor, se le solicitará que lo configure ahora.</span><span class="sxs-lookup"><span data-stu-id="bd1f1-120">If the server against which the wizard is running has not yet been configured as a Distributor, you are prompted to configure it now.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1f1-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd1f1-121">See Also</span></span>  
 [<span data-ttu-id="bd1f1-122">Crear una publicación a partir de una base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="bd1f1-122">Create a Publication from an Oracle Database</span></span>](publish/create-a-publication-from-an-oracle-database.md)   

  
  
