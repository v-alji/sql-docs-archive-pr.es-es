---
title: Propiedades del suscriptor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.subscribers.f1
helpviewer_keywords:
- Subscriber Properties dialog box
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81ab9cf5f277ccfe1044e5a7083f019db9d843ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749702"
---
# <a name="subscriber-properties"></a><span data-ttu-id="d315e-102">Propiedades del suscriptor</span><span class="sxs-lookup"><span data-stu-id="d315e-102">Subscriber Properties</span></span>
  <span data-ttu-id="d315e-103">El cuadro de diálogo **Propiedades del suscriptor** contiene información relevante para los suscriptores que ejecutan versiones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a la [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d315e-103">The **Subscriber Properties** dialog box contains information relevant to Subscribers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="d315e-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="d315e-104">Options</span></span>  
 <span data-ttu-id="d315e-105">**Conexión del agente al suscriptor**</span><span class="sxs-lookup"><span data-stu-id="d315e-105">**Agent Connection to the Subscriber**</span></span>  
 <span data-ttu-id="d315e-106">Contexto bajo el que el Agente de distribución y el Agente de mezcla conectan desde el distribuidor al suscriptor. Se aplica solamente a versiones anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d315e-106">The context under which the Distribution Agent and Merge Agent connect from the Distributor to the Subscriber This applies only to versions before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="d315e-107">Seleccione **Suplantar cuenta de proceso del agente** para establecer conexiones al suscriptor a través del contexto de la cuenta del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el distribuidor, o especifique **Autenticación de SQL Server**y escriba un valor para **Inicio de sesión** y **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="d315e-107">Select **Impersonate agent process account** to make connections to the Subscriber using the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent account at the Distributor, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d315e-108">recomienda que se seleccione **Suplantar cuenta de proceso del agente**.</span><span class="sxs-lookup"><span data-stu-id="d315e-108">recommends that you select **Impersonate agent process account**.</span></span>  
  
 <span data-ttu-id="d315e-109">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores la información de conexión se especifica para cada suscripción en el Asistente para nueva suscripción y puede cambiar en el cuadro de diálogo **Propiedades de suscripción** .</span><span class="sxs-lookup"><span data-stu-id="d315e-109">For [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, connection information is specified for each subscription in the New Subscription Wizard and can be changed in the **Subscription Properties** dialog box.</span></span>  
  
 <span data-ttu-id="d315e-110">**Programaciones predeterminadas del agente**</span><span class="sxs-lookup"><span data-stu-id="d315e-110">**Default Agent Schedules**</span></span>  
 <span data-ttu-id="d315e-111">Programación predeterminada utilizada en el Asistente para nueva suscripción para suscriptores que ejecutan versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d315e-111">The default schedule used in the New Subscription Wizard for Subscribers running versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
 <span data-ttu-id="d315e-112">**Varios**</span><span class="sxs-lookup"><span data-stu-id="d315e-112">**Miscellaneous**</span></span>  
 <span data-ttu-id="d315e-113">Incluye información sobre el suscriptor y el tipo de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="d315e-113">Includes information on the Subscriber and Subscriber type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d315e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d315e-114">See Also</span></span>  
 [<span data-ttu-id="d315e-115">Ver y modificar las propiedades del distribuidor y del publicador</span><span class="sxs-lookup"><span data-stu-id="d315e-115">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

 [<span data-ttu-id="d315e-116">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="d315e-116">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
