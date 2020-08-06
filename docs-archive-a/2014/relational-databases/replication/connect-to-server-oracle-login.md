---
title: Conexión al servidor (Oracle), Inicio de sesión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23f5b515fcb1e80416d860e2ff3a2e6be5431819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662838"
---
# <a name="connect-to-server-oracle-login"></a><span data-ttu-id="b73bf-102">Conectar al servidor (Oracle), Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="b73bf-102">Connect to Server (Oracle), Login</span></span>
  <span data-ttu-id="b73bf-103">Use la pestaña **Inicio de sesión** del cuadro de diálogo **Conectar al servidor** para especificar la cuenta desde la que se van a realizar las conexiones del distribuidor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el publicador de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b73bf-103">Use the **Login** tab of the **Connect to Server** dialog box to specify the account under which connections are made from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher.</span></span> <span data-ttu-id="b73bf-104">Se debe usar la misma cuenta que se especificó para el esquema de usuario administrativo de replicación al configurar el publicador.</span><span class="sxs-lookup"><span data-stu-id="b73bf-104">You must use the same account as the one specified for the replication administrative user schema during configuration of the Publisher.</span></span> <span data-ttu-id="b73bf-105">Para obtener más información, vea [Configurar un publicador de Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="b73bf-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b73bf-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="b73bf-106">Options</span></span>  
 <span data-ttu-id="b73bf-107">**Instancia del servidor**</span><span class="sxs-lookup"><span data-stu-id="b73bf-107">**Server instance**</span></span>  
 <span data-ttu-id="b73bf-108">Nombre TNS (Transparent Network Substrate, Sustrato de red transparente) del publicador de Oracle, que se especifica durante la configuración del software de cliente Oracle instalado en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="b73bf-108">The Transparent Network Substrate (TNS) name of the Oracle Publisher, which is specified during configuration of the Oracle client software installed on the Distributor.</span></span>  
  
 <span data-ttu-id="b73bf-109">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="b73bf-109">**Authentication**</span></span>  
 <span data-ttu-id="b73bf-110">Seleccione **Autenticación estándar de Oracle** (opción recomendada) o **Autenticación de Windows**.</span><span class="sxs-lookup"><span data-stu-id="b73bf-110">Select **Oracle Standard Authentication** (recommended) or **Windows Authentication**.</span></span> <span data-ttu-id="b73bf-111">Si selecciona **Autenticación de Windows**:</span><span class="sxs-lookup"><span data-stu-id="b73bf-111">If you select **Windows Authentication**:</span></span>  
  
-   <span data-ttu-id="b73bf-112">El servidor de Oracle debe configurarse de forma que permita conexiones con las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="b73bf-112">The Oracle server must be configured to allow connections using Windows credentials.</span></span> <span data-ttu-id="b73bf-113">Para obtener más información, vea la documentación de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b73bf-113">For more information, see the Oracle documentation.</span></span>  
  
-   <span data-ttu-id="b73bf-114">Debe haber iniciado una sesión con la misma cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows que especificó para el esquema de usuario administrativo de replicación.</span><span class="sxs-lookup"><span data-stu-id="b73bf-114">You must be currently logged in with the same [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account you specified for the replication administrative user schema.</span></span>  
  
 <span data-ttu-id="b73bf-115">**Inicio de sesión** y **Contraseña**</span><span class="sxs-lookup"><span data-stu-id="b73bf-115">**Login** and **Password**</span></span>  
 <span data-ttu-id="b73bf-116">Si selecciona **Autenticación estándar de Oracle** para la opción **Autenticación** , especifique el nombre de inicio de sesión y la contraseña; deben coincidir con los especificados para el esquema de usuario administrativo de replicación.</span><span class="sxs-lookup"><span data-stu-id="b73bf-116">If you selected **Oracle Standard Authentication** for the **Authentication** option, specify the login and password to use, which must be the same as those specified for the replication administrative user schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73bf-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b73bf-117">See Also</span></span>  
 [<span data-ttu-id="b73bf-118">Glosario de términos de publicaciones de Oracle</span><span class="sxs-lookup"><span data-stu-id="b73bf-118">Glossary of Terms for Oracle Publishing</span></span>](non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
