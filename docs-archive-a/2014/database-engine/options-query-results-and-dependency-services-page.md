---
title: Opciones (página resultados de la consulta y servicios de dependencia) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.DependencyServicesGeneral
ms.assetid: dd7f6c31-7d7f-4972-854a-1419a2826dca
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 356714ee933fb40eda7038f4088309b6187f3ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676171"
---
# <a name="options-query-results-and-dependency-services-page"></a><span data-ttu-id="d1caf-102">Opciones (Resultados de la consulta/página Servicios de dependencia)</span><span class="sxs-lookup"><span data-stu-id="d1caf-102">Options (Query Results and Dependency Services Page)</span></span>
  <span data-ttu-id="d1caf-103">Utilice esta página para especificar el servidor al que desea conectarse para Servicios de dependencia.</span><span class="sxs-lookup"><span data-stu-id="d1caf-103">Use this page to specify the server to connect for Dependency Services.</span></span> <span data-ttu-id="d1caf-104">Servicios de dependencia le permite extraer información sobre las dependencias existentes entre los objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y los de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] almacenados en servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="d1caf-104">Dependency Services enables you to extract information about dependencies between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects stored on different servers.</span></span> <span data-ttu-id="d1caf-105">Puede ver las dependencias de los objetos mediante el cuadro de diálogo **dependencias del objeto** de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1caf-105">You view object dependencies by using the **Object Dependencies** dialog box in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="d1caf-106">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="d1caf-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="d1caf-107">Abrir el cuadro de diálogo Opciones (página Resultados de la consulta/Servicios de dependencia)</span><span class="sxs-lookup"><span data-stu-id="d1caf-107">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="d1caf-108">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="d1caf-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-options-query-resultsdependency-services-page-dialog-box"></a><a name="open_dialog"></a><span data-ttu-id="d1caf-109">Abrir el cuadro de diálogo Opciones (página resultados de la consulta/servicios de dependencia)</span><span class="sxs-lookup"><span data-stu-id="d1caf-109">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>  
  
1.  <span data-ttu-id="d1caf-110">En [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , haga clic en **Opciones** en el menú **herramientas** .</span><span class="sxs-lookup"><span data-stu-id="d1caf-110">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="d1caf-111">Expanda **Resultados de la consulta** y, después, haga clic en **Servicios de dependencia**.</span><span class="sxs-lookup"><span data-stu-id="d1caf-111">Expand **Query Results**, and then click **Dependency Services**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="d1caf-112">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="d1caf-112">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="d1caf-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="d1caf-113">Options</span></span>  
 <span data-ttu-id="d1caf-114">**Servidor de los servicios de dependencia.**</span><span class="sxs-lookup"><span data-stu-id="d1caf-114">**Dependency Services server**</span></span>  
 <span data-ttu-id="d1caf-115">Especifique el servidor en el que está instalado Servicios de dependencia.</span><span class="sxs-lookup"><span data-stu-id="d1caf-115">Specify the server that Dependency Services is installed on.</span></span>  
  
 <span data-ttu-id="d1caf-116">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="d1caf-116">**Authentication**</span></span>  
 <span data-ttu-id="d1caf-117">Seleccione Autenticación de Windows para iniciar sesión con una cuenta de usuario de Microsoft Windows o seleccione Autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1caf-117">Select Windows Authentication to log on using a Microsoft Windows user account, or select SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d1caf-118">Cuando un usuario se conecta con un nombre y una contraseña de inicio de sesión determinados desde una conexión que no es de confianza, SQL Server realiza la autenticación y comprueba si se ha configurado una cuenta de inicio de sesión de SQL Server y si la contraseña especificada coincide con la almacenada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d1caf-118">When a user connects with a specified login name and password from a non-trusted connection, SQL Server performs the authentication by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="d1caf-119">Si SQL Server no encuentra la cuenta de inicio de sesión, la autenticación no se realizará correctamente y el usuario recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d1caf-119">If SQL Server cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="d1caf-120">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="d1caf-120">**User name**</span></span>  
 <span data-ttu-id="d1caf-121">Si utiliza Autenticación de SQL Server, proporcione un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="d1caf-121">If using SQL Server Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="d1caf-122">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d1caf-122">**Password**</span></span>  
 <span data-ttu-id="d1caf-123">Si está utilizando Autenticación de SQL Server, proporcione una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d1caf-123">If using SQL Server Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="d1caf-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="d1caf-124">**Test**</span></span>  
 <span data-ttu-id="d1caf-125">Haga clic en esta opción para comprobar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d1caf-125">Click to test the connection.</span></span>