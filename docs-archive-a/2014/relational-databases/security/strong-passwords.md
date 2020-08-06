---
title: Contraseñas seguras | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745110"
---
# <a name="strong-passwords"></a><span data-ttu-id="0dfde-102">Contraseñas seguras</span><span class="sxs-lookup"><span data-stu-id="0dfde-102">Strong Passwords</span></span>
  <span data-ttu-id="0dfde-103">Las contraseñas pueden constituir el vínculo más débil de una implementación de seguridad de servidor.</span><span class="sxs-lookup"><span data-stu-id="0dfde-103">Passwords can be the weakest link in a server security deployment.</span></span> <span data-ttu-id="0dfde-104">Debe tener siempre mucho cuidado a la hora de elegir una contraseña.</span><span class="sxs-lookup"><span data-stu-id="0dfde-104">You should always take great care when you select a password.</span></span> <span data-ttu-id="0dfde-105">Una contraseña segura presenta las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="0dfde-105">A strong password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="0dfde-106">Tiene una longitud de 8 caracteres como mínimo.</span><span class="sxs-lookup"><span data-stu-id="0dfde-106">Is at least 8 characters long.</span></span>  
  
-   <span data-ttu-id="0dfde-107">Contiene una combinación de letras, números y símbolos.</span><span class="sxs-lookup"><span data-stu-id="0dfde-107">Combines letters, numbers, and symbol characters within the password.</span></span>  
  
-   <span data-ttu-id="0dfde-108">No es una palabra que pueda encontrarse en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="0dfde-108">Is not found in a dictionary.</span></span>  
  
-   <span data-ttu-id="0dfde-109">No es el nombre de un comando.</span><span class="sxs-lookup"><span data-stu-id="0dfde-109">Is not the name of a command.</span></span>  
  
-   <span data-ttu-id="0dfde-110">No es el nombre de una persona.</span><span class="sxs-lookup"><span data-stu-id="0dfde-110">Is not the name of a person.</span></span>  
  
-   <span data-ttu-id="0dfde-111">No es el nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0dfde-111">Is not the name of a user.</span></span>  
  
-   <span data-ttu-id="0dfde-112">No es el nombre de un equipo.</span><span class="sxs-lookup"><span data-stu-id="0dfde-112">Is not the name of a computer.</span></span>  
  
-   <span data-ttu-id="0dfde-113">Se cambia con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="0dfde-113">Is changed regularly.</span></span>  
  
-   <span data-ttu-id="0dfde-114">Presenta diferencias notables con respecto a contraseñas anteriores.</span><span class="sxs-lookup"><span data-stu-id="0dfde-114">Is significantly different from previous passwords.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="0dfde-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden contener hasta 128 caracteres, entre los que se pueden incluir letras, símbolos y dígitos.</span><span class="sxs-lookup"><span data-stu-id="0dfde-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain up to 128 characters, including letters, symbols, and digits.</span></span> <span data-ttu-id="0dfde-116">Dado que los inicios de sesión, nombres de usuario, roles y contraseñas se utilizan con frecuencia en instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] , determinados símbolos deberán estar incluidos entre comillas dobles (") o corchetes ([ ]).</span><span class="sxs-lookup"><span data-stu-id="0dfde-116">Because logins, user names, roles, and passwords are frequently used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, certain symbols must be enclosed by double quotation marks (") or square brackets ([ ]).</span></span> <span data-ttu-id="0dfde-117">Utilice estos delimitadores en las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] cuando el inicio de sesión, usuario, rol o contraseña de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] presente las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="0dfde-117">Use these delimiters in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, user, role, or password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="0dfde-118">Contiene o comienza por un carácter de espacio.</span><span class="sxs-lookup"><span data-stu-id="0dfde-118">Contains or starts with a space character.</span></span>  
  
-   <span data-ttu-id="0dfde-119">Comienza por el carácter $ o \@.</span><span class="sxs-lookup"><span data-stu-id="0dfde-119">Starts with the $ or \@ character.</span></span>  
  
 <span data-ttu-id="0dfde-120">Si se usa en una cadena de conexión de OLE DB u ODBC, el inicio de sesión o la contraseña no deben contener ninguno de estos caracteres: [] {}() , ; ?</span><span class="sxs-lookup"><span data-stu-id="0dfde-120">If used in an OLE DB or ODBC connection string, a login or password must not contain the following characters: [] {}() , ; ?</span></span> <span data-ttu-id="0dfde-121">\* !</span><span class="sxs-lookup"><span data-stu-id="0dfde-121">\* !</span></span> <span data-ttu-id="0dfde-122">\@.</span><span class="sxs-lookup"><span data-stu-id="0dfde-122">\@.</span></span> <span data-ttu-id="0dfde-123">Estos caracteres se usan para inicializar una conexión o para separar valores de conexión.</span><span class="sxs-lookup"><span data-stu-id="0dfde-123">These characters are used to either initialize a connection or separate connection values.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="0dfde-124">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0dfde-124">Related Content</span></span>  
 [<span data-ttu-id="0dfde-125">Directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0dfde-125">Password Policy</span></span>](password-policy.md)  
  
  
