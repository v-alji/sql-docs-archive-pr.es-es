---
title: MSSQLSERVER_17832 | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17828 (Database Engine error)
- maxtokensize
- 17832 (Database Engine error)
- login packet (bad)
ms.assetid: bd56ffe4-0855-4ada-8aca-251fbc6ff2ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dba214e2cce04ff2583e12ae7cee9b54373390a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744729"
---
# <a name="mssqlserver_17832"></a><span data-ttu-id="7a08d-102">MSSQLSERVER_17832</span><span class="sxs-lookup"><span data-stu-id="7a08d-102">MSSQLSERVER_17832</span></span>
    
## <a name="details"></a><span data-ttu-id="7a08d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7a08d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a08d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7a08d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7a08d-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7a08d-105">Event ID</span></span>|<span data-ttu-id="7a08d-106">17832</span><span class="sxs-lookup"><span data-stu-id="7a08d-106">17832</span></span>|  
|<span data-ttu-id="7a08d-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7a08d-107">Event Source</span></span>|<span data-ttu-id="7a08d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7a08d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7a08d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7a08d-109">Component</span></span>|<span data-ttu-id="7a08d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7a08d-110">SQLEngine</span></span>|  
|<span data-ttu-id="7a08d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7a08d-111">Symbolic Name</span></span>|<span data-ttu-id="7a08d-112">SRV_BAD_LOGIN_PKT</span><span class="sxs-lookup"><span data-stu-id="7a08d-112">SRV_BAD_LOGIN_PKT</span></span>|  
|<span data-ttu-id="7a08d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7a08d-113">Message Text</span></span>|<span data-ttu-id="7a08d-114">La estructura del paquete de inicio de sesión utilizado para abrir la conexión no es válida; se cerró la conexión.</span><span class="sxs-lookup"><span data-stu-id="7a08d-114">The login packet used to open the connection is structurally invalid; the connection has been closed.</span></span> <span data-ttu-id="7a08d-115">Póngase en contacto con el proveedor de la biblioteca cliente.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="7a08d-115">Please contact the vendor of the client library.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7a08d-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7a08d-116">Explanation</span></span>  
 <span data-ttu-id="7a08d-117">El equipo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pudo procesar el paquete de inicio de sesión de cliente.</span><span class="sxs-lookup"><span data-stu-id="7a08d-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer was unable to process the client login packet.</span></span> <span data-ttu-id="7a08d-118">Esto puede deberse a que el paquete se creó incorrectamente o a que se dañó durante la transmisión.</span><span class="sxs-lookup"><span data-stu-id="7a08d-118">This may be because the packet was created improperly or because the packet was damaged during transmission.</span></span> <span data-ttu-id="7a08d-119">También puede deberse a la configuración del equipo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a08d-119">It can also be caused by the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="7a08d-120">La dirección IP enumerada es la del equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="7a08d-120">The IP address listed is the address of the client computer.</span></span>  
  
### <a name="more-information"></a><span data-ttu-id="7a08d-121">Más información</span><span class="sxs-lookup"><span data-stu-id="7a08d-121">More Information</span></span>  
 <span data-ttu-id="7a08d-122">Al utilizar la autenticación de Windows en un entorno de Kerberos, un cliente recibe un vale de Kerberos que contiene un certificado de atributos de privilegios (PAC).</span><span class="sxs-lookup"><span data-stu-id="7a08d-122">When using Windows Authentication in a Kerberos environment, a client receives a Kerberos ticket that contains a Privilege Attribute Certificate (PAC).</span></span> <span data-ttu-id="7a08d-123">El PAC contiene varios tipos de datos de autorización incluidos los grupos de los que el usuario es miembro, los derechos de los que el usuario dispone y qué directivas se le aplican.</span><span class="sxs-lookup"><span data-stu-id="7a08d-123">The PAC contains various types of authorization data including groups that the user is a member of, rights the user has, and what policies apply to the user.</span></span> <span data-ttu-id="7a08d-124">Cuando el cliente recibe el vale de Kerberos, la información contenida en el PAC se utiliza para generar el token de acceso del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a08d-124">When the client receives the Kerberos ticket, the information contained in the PAC is used to generate the user's access token.</span></span> <span data-ttu-id="7a08d-125">El cliente presenta el token al equipo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como parte del paquete de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="7a08d-125">The client presents the token to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer as part of the login packet.</span></span>  
  
 <span data-ttu-id="7a08d-126">Si el token se creó incorrectamente o se dañó durante la transmisión, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no puede proporcionar información adicional sobre el problema.</span><span class="sxs-lookup"><span data-stu-id="7a08d-126">If the token was improperly created or damaged during transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot offer additional information about the problem.</span></span>  
  
 <span data-ttu-id="7a08d-127">Cuando el usuario es miembro de muchos grupos o tiene muchas directivas, el token puede crecer más de lo normal como para mostrarlo todo.</span><span class="sxs-lookup"><span data-stu-id="7a08d-127">When the user is a member of many groups or has many policies, the token may grow larger than normal to list them all.</span></span> <span data-ttu-id="7a08d-128">Si el token aumenta de tamaño por encima del valor de **MaxTokenSize** del equipo servidor, el cliente no puede conectarse, emite un error general de red (GNE) y se puede producir el error 17832.</span><span class="sxs-lookup"><span data-stu-id="7a08d-128">If the token grows larger than the **MaxTokenSize** value of the server computer, the client fails to connect with a General Network Error (GNE) and error 17832 can occur.</span></span> <span data-ttu-id="7a08d-129">Este problema puede afectar solo a algunos usuarios: los usuarios con muchos grupos o directivas.</span><span class="sxs-lookup"><span data-stu-id="7a08d-129">This problem may affect only some users: users with many groups or policies.</span></span> <span data-ttu-id="7a08d-130">Cuando el problema es el valor **MaxTokenSize** del equipo servidor, el error 17832 del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estará acompañado de un error con el estado 9.</span><span class="sxs-lookup"><span data-stu-id="7a08d-130">When the problem is the **MaxTokenSize** value of the server computer, error 17832 in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log will be accompanied by an error with state 9.</span></span> <span data-ttu-id="7a08d-131">Para obtener más información sobre Kerberos y **MaxTokenSize**, vea [KB327825](https://support.microsoft.com/kb/327825).</span><span class="sxs-lookup"><span data-stu-id="7a08d-131">For additional details about the Kerberos and **MaxTokenSize**, see [KB327825](https://support.microsoft.com/kb/327825).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a08d-132">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7a08d-132">User Action</span></span>  
 <span data-ttu-id="7a08d-133">Para resolver este problema, aumente el valor de **MaxTokenSize** del equipo servidor a un tamaño lo suficientemente grande como para contener el token de mayor tamaño de cualquier usuario de la organización.</span><span class="sxs-lookup"><span data-stu-id="7a08d-133">To resolve this problem, increase the **MaxTokenSize** value of the server computer, to a size large enough to contain the largest token of any user in your organization.</span></span> <span data-ttu-id="7a08d-134">Para averiguar el tamaño correcto del token para la organización, considere usar la aplicación **Tokensz**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-134">To research the correct token size for your organization, consider using the **Tokensz** application.</span></span>   
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="7a08d-135">**Para cambiar el MaxTokenSize en el equipo servidor**</span><span class="sxs-lookup"><span data-stu-id="7a08d-135">**To change the MaxTokenSize  on the server computer**</span></span>  
  
1.  <span data-ttu-id="7a08d-136">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-136">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="7a08d-137">Escriba `regedit` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-137">Type `regedit`, and then click **OK**.</span></span> <span data-ttu-id="7a08d-138">(Si aparece el cuadro de diálogo **Control de cuentas de usuario**, haga clic en **Continuar**).</span><span class="sxs-lookup"><span data-stu-id="7a08d-138">(If the **User Account Control** dialog box appears, click **Continue**.)</span></span>  
  
3.  <span data-ttu-id="7a08d-139">Desplácese a **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-139">Navigate to **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span></span>  
  
4.  <span data-ttu-id="7a08d-140">Si el parámetro **MaxTokenSize** no está presente, haga clic con el botón derecho en **Parameters**, seleccione **Nuevo** y haga clic en Valor de **DWORD (32 bits)** .</span><span class="sxs-lookup"><span data-stu-id="7a08d-140">If the **MaxTokenSize** parameter is not present, right-click **Parameters**, point to **New**, and then click **DWORD (32-bit)** Value.</span></span> <span data-ttu-id="7a08d-141">Denomine a la entrada del Registro **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-141">Name the registry entry **MaxTokenSize**.</span></span>  
  
5.  <span data-ttu-id="7a08d-142">Haga clic con el botón derecho en **MaxTokenSize** y, a continuación, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-142">Right-click **MaxTokenSize**, and then click **Modify**.</span></span>  
  
6.  <span data-ttu-id="7a08d-143">En el tipo de cuadro **Información del valor**, escriba el valor de **MaxTokenSize** que quiera.</span><span class="sxs-lookup"><span data-stu-id="7a08d-143">In the **Value data** box type the desired **MaxTokenSize** value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a08d-144">El valor ffff hexadecimal (valor decimal 65535) es el tamaño máximo recomendado del token.</span><span class="sxs-lookup"><span data-stu-id="7a08d-144">Hexadecimal value ffff (decimal value 65535) is the maximum recommended token size.</span></span> <span data-ttu-id="7a08d-145">Si se proporciona este valor, probablemente el problema se resolvería, pero podría tener efectos adversos en todo el equipo con respecto al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7a08d-145">Providing this value would probably solve the problem, but could have negative computer-wide effects with regard to performance.</span></span> <span data-ttu-id="7a08d-146">Recomendamos que establezca el menor valor de **MaxTokenSize** que permita el token de mayor tamaño de cualquier usuario de la organización e introduzca ese valor.</span><span class="sxs-lookup"><span data-stu-id="7a08d-146">We recommend that you establish the minimum **MaxTokenSize** value that allows for the largest token of any user in your organization and enter that value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="7a08d-147">Cierre el **Editor del Registro**.</span><span class="sxs-lookup"><span data-stu-id="7a08d-147">Close **Registry Editor**.</span></span>  
  
9. <span data-ttu-id="7a08d-148">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="7a08d-148">Restart the computer.</span></span>  
  
  
