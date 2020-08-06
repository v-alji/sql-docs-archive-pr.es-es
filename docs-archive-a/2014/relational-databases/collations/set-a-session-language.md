---
title: Establecer un idioma de la sesión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], international considerations
- globalization [SQL Server], sessions
- time [SQL Server]
- sessions [SQL Server], languages
- international considerations [SQL Server], sessions
- dates [SQL Server], session languages
- global considerations [SQL Server], sessions
- client-side session language
- time [SQL Server], session languages
- messages [SQL Server], international considerations
- server-side session language
ms.assetid: de7f2c90-8f4f-4cfc-94cc-4933a7fd2bde
author: stevestein
ms.author: sstein
ms.openlocfilehash: da8d6adce66ac5b97e533b5afaefabda40e4b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677696"
---
# <a name="set-a-session-language"></a><span data-ttu-id="abcac-102">Establecer un idioma de la sesión</span><span class="sxs-lookup"><span data-stu-id="abcac-102">Set a Session Language</span></span>
  <span data-ttu-id="abcac-103">El idioma de la sesión se puede utilizar para establecer la forma en que se muestran los siguientes elementos en el servidor, dependiendo de la preferencia cultural y de idioma:</span><span class="sxs-lookup"><span data-stu-id="abcac-103">The session language can be used to set how the following elements are displayed on the server, based on language and cultural preference:</span></span>  
  
-   <span data-ttu-id="abcac-104">El lenguaje que se usará para los mensajes de error y otros mensajes del sistema.</span><span class="sxs-lookup"><span data-stu-id="abcac-104">The language that will be used for error and other system messages.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="abcac-105">admite varias copias de todas las cadenas de error del sistema y mensajes en todos los idiomas en los que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está disponible.</span><span class="sxs-lookup"><span data-stu-id="abcac-105">supports having multiple copies of all system error strings and messages in all the languages in which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is available.</span></span> <span data-ttu-id="abcac-106">Estos mensajes se pueden ver en la vista de catálogo [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) .</span><span class="sxs-lookup"><span data-stu-id="abcac-106">These messages can be viewed in the [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) catalog view.</span></span> <span data-ttu-id="abcac-107">Cuando se instala una versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], estos mensajes del sistema se traducen a la versión de idioma que se instala.</span><span class="sxs-lookup"><span data-stu-id="abcac-107">When you install a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], these system messages are translated for the language version that you install.</span></span> <span data-ttu-id="abcac-108">También se obtiene de forma predeterminada. El conjunto en inglés de EE.UU. de estos mensajes</span><span class="sxs-lookup"><span data-stu-id="abcac-108">By default, you also obtain the U.S. English set of these messages.</span></span> <span data-ttu-id="abcac-109">Además, se pueden agregar mensajes definidos por el usuario en un idioma específico con [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="abcac-109">Additionally, you can add user-defined messages in a specific language by using [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span></span>  
  
-   <span data-ttu-id="abcac-110">El formato de los datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="abcac-110">The format of date and time data.</span></span>  
  
-   <span data-ttu-id="abcac-111">Los nombres de días y meses, incluidas las abreviaturas.</span><span class="sxs-lookup"><span data-stu-id="abcac-111">The names of days and months, including abbreviations.</span></span>  
  
-   <span data-ttu-id="abcac-112">El primer día de la semana.</span><span class="sxs-lookup"><span data-stu-id="abcac-112">The first day of the week.</span></span>  
  
-   <span data-ttu-id="abcac-113">Los datos de moneda.</span><span class="sxs-lookup"><span data-stu-id="abcac-113">Currency data.</span></span>  
  
 <span data-ttu-id="abcac-114">Existen 33 idiomas disponibles para ser utilizados como valores de la sesión.</span><span class="sxs-lookup"><span data-stu-id="abcac-114">There are 33 languages available for use as session settings.</span></span> <span data-ttu-id="abcac-115">Para obtener una lista de los idiomas, vea [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="abcac-115">For a list of languages, see [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-server"></a><span data-ttu-id="abcac-116">Configurar el idioma de la sesión desde el servidor</span><span class="sxs-lookup"><span data-stu-id="abcac-116">Setting the Session Language from the Server</span></span>  
 <span data-ttu-id="abcac-117">Para establecer el idioma de la sesión desde el servidor, utilice [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="abcac-117">To set the session language from the server side, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-client"></a><span data-ttu-id="abcac-118">Configurar el idioma de la sesión desde el cliente</span><span class="sxs-lookup"><span data-stu-id="abcac-118">Setting the Session Language from the Client</span></span>  
 <span data-ttu-id="abcac-119">El idioma de la sesión se puede establecer del lado cliente con OLE DB, ODBC o ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="abcac-119">The session language can be set on the client side by using OLE DB, ODBC or ADO.NET.</span></span> <span data-ttu-id="abcac-120">Para OLE DB, utilice la propiedad SSPROP_INIT_CURRENTLANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="abcac-120">For OLE DB, use the SSPROP_INIT_CURRENTLANGUAGE property.</span></span> <span data-ttu-id="abcac-121">Para obtener más información, vea [Propiedades de inicialización y autorización](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="abcac-121">For more information, see [Initialization and Authorization Properties](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
 <span data-ttu-id="abcac-122">Para ODBC, utilice la palabra clave Language.</span><span class="sxs-lookup"><span data-stu-id="abcac-122">For ODBC, use the Language keyword.</span></span> <span data-ttu-id="abcac-123">Para más información, consulte [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="abcac-123">For more information, see [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="abcac-124">Para ADO.NET, utilice el parámetro **Current Language** del objeto **ConnectionString** .</span><span class="sxs-lookup"><span data-stu-id="abcac-124">For ADO.NET, use the **Current Language** parameter of the **ConnectionString** object.</span></span> <span data-ttu-id="abcac-125">Para obtener más información, vea la documentación del kit de desarrollo de software (SDK) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC).</span><span class="sxs-lookup"><span data-stu-id="abcac-125">For more information, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) software development kit (SDK) documentation.</span></span>  
  
  
