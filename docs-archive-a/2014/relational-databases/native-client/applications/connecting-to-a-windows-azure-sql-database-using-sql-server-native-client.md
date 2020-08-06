---
title: Conexión a un Azure SQL Database mediante SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0dc20bb6-b142-4259-b87b-427d2ba798af
author: rothja
ms.author: jroth
ms.openlocfilehash: 177c655f97e32f2044460e87c6cd775cdf8fcde9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674070"
---
# <a name="connecting-to-an-azure-sql-database-using-sql-server-native-client"></a><span data-ttu-id="a06fc-102">Conexión a una Azure SQL Database con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a06fc-102">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>
  <span data-ttu-id="a06fc-103">Para obtener un ejemplo que muestra cómo conectarse a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] mediante [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, vea [desarrollo: temas de procedimientos (Azure SQL Database)](https://msdn.microsoft.com/library/ee621787.aspx).</span><span class="sxs-lookup"><span data-stu-id="a06fc-103">For a sample that shows how to connect to a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Development: How-to Topics (Azure SQL Database)](https://msdn.microsoft.com/library/ee621787.aspx).</span></span>  
  
## <a name="known-issues-when-connecting-to-a-sql-database"></a><span data-ttu-id="a06fc-104">Problemas conocidos para conectarse a una SQL Database</span><span class="sxs-lookup"><span data-stu-id="a06fc-104">Known Issues When Connecting to a SQL Database</span></span>  
 <span data-ttu-id="a06fc-105">A continuación se describen problemas conocidos para conectarse a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] mediante [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span><span class="sxs-lookup"><span data-stu-id="a06fc-105">The following are known issues when connecting to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   <span data-ttu-id="a06fc-106">Una conexión realizada con `SQLBrowseConnect` puede rechazarse si `SQLBrowseConnect` se utiliza en etapas.</span><span class="sxs-lookup"><span data-stu-id="a06fc-106">A connection made with `SQLBrowseConnect` may be rejected if `SQLBrowseConnect` is used in stages.</span></span>  <span data-ttu-id="a06fc-107">Por ejemplo, si el nombre del controlador se envía en la primera llamada, el servidor y las credenciales (usuario y contraseña) se envían en la segunda llamada y establecen la conexión, y un nombre de base de datos y un idioma en la tercera llamada.</span><span class="sxs-lookup"><span data-stu-id="a06fc-107">For example, if the driver name is sent in the first call, server and credentials (user and password) sent in the second call, establishing the connection, and a database name and a language in the third call.</span></span>  <span data-ttu-id="a06fc-108">La tercera llamada hara que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client emita una instrucción USE para cambiar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a06fc-108">The third call will cause [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to issue a USE statement to change databases.</span></span> <span data-ttu-id="a06fc-109">Sin embargo, la instrucción USE no se admite en [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], que produce el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="a06fc-109">However, the USE statement is not supported in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], generating the following error:</span></span>  
  
    ```  
    [Microsoft][SQL Server Native Client 11.0][SQL Server]USE statement is not supported to switch between databases. Use a new connection to connect to a different Database.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a06fc-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a06fc-110">See Also</span></span>  
 [<span data-ttu-id="a06fc-111">Generar aplicaciones con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a06fc-111">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
