---
title: Propiedades de Configuración de SQL Server Native Client (pestaña Marcas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3ca7b87963fc3848bbb933a5c21f9d608d37d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676747"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a><span data-ttu-id="ada14-102">Propiedades de Configuración de SQL Server Native Client (pestaña Marcas)</span><span class="sxs-lookup"><span data-stu-id="ada14-102">SQL Server Native Client Configuration Properties (Flags Tab)</span></span>
  <span data-ttu-id="ada14-103">Los clientes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de este equipo se comunican con los servidores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante los protocolos suministrados en el archivo de biblioteca de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="ada14-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this machine, communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers using the protocols provided in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client library file.</span></span> <span data-ttu-id="ada14-104">En esta página se configura el equipo cliente para solicitar una conexión cifrada mediante Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="ada14-104">This page provides configures the client computer to request an encrypted connection using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="ada14-105">Si no es posible establecer una conexión cifrada, la conexión no se establecerá.</span><span class="sxs-lookup"><span data-stu-id="ada14-105">If an encrypted connection cannot be established, the connection will fail.</span></span>  
  
 <span data-ttu-id="ada14-106">El proceso de inicio de sesión siempre está cifrado.</span><span class="sxs-lookup"><span data-stu-id="ada14-106">The login process is always encrypted.</span></span> <span data-ttu-id="ada14-107">Las opciones que se facilitan a continuación solo se aplican al cifrado de datos.</span><span class="sxs-lookup"><span data-stu-id="ada14-107">The options below apply only to encrypting data.</span></span> <span data-ttu-id="ada14-108">Para más información sobre cómo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cifra la comunicación e instrucciones sobre cómo configurar el cliente para que confíe en la entidad de certificación raíz del certificado de servidor, vea "Cifrar conexiones a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" y "Cómo habilitar conexiones cifradas en el [!INCLUDE[ssDE](../../includes/ssde-md.md)] (Administrador de configuración de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] )" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ada14-108">For more information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encrypts communication and for instructions on how to configure the client to trust the root authority of the server certificate, see "Encrypting Connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" and "How to: Enable Encrypted Connections to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ada14-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="ada14-109">Options</span></span>  
 <span data-ttu-id="ada14-110">**ForceEncryption**</span><span class="sxs-lookup"><span data-stu-id="ada14-110">**Force protocol encryption**</span></span>  
 <span data-ttu-id="ada14-111">Solicita una conexión con SSL.</span><span class="sxs-lookup"><span data-stu-id="ada14-111">Request a connection using SSL.</span></span>  
  
 <span data-ttu-id="ada14-112">**TrustServerCertificate**</span><span class="sxs-lookup"><span data-stu-id="ada14-112">**Trust Server Certificate**</span></span>  
 <span data-ttu-id="ada14-113">Cuando se establece en **No**, el proceso de cliente intenta validar el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="ada14-113">When set to **No**, the client process attempts to validate the server certificate.</span></span> <span data-ttu-id="ada14-114">El cliente y el servidor deben tener cada uno un certificado emitido por una entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="ada14-114">The client and server must have each have a certificate issues from a public certification authority.</span></span> <span data-ttu-id="ada14-115">Si el certificado no está presente en el equipo cliente o no se puede validar, la conexión finalizará.</span><span class="sxs-lookup"><span data-stu-id="ada14-115">If the certificate is not present on the client computer, or if the validation of the certificate fails, the connection is terminated.</span></span>  
  
 <span data-ttu-id="ada14-116">Si se establece en **Yes**, el cliente no validará el certificado de servidor, por lo que se habilitará el uso de un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="ada14-116">When set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span>  
  
 <span data-ttu-id="ada14-117">**Confiar en certificado de servidor** solo está disponible si **Forzar cifrado de protocolos** se ha establecido en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ada14-117">**Trust Server Certificate** is only available if **Force protocol encryption** is set to **Yes**.</span></span>  
  
  
