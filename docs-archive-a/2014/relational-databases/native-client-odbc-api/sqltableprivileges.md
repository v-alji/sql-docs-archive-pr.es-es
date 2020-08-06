---
title: SQLTablePrivileges | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTablePrivileges function
ms.assetid: 8cce22d5-28b1-4b50-a5bc-1de03e0ffd6b
author: rothja
ms.author: jroth
ms.openlocfilehash: 63298330d3f0ebf707dbb42c337553c1f363deab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672952"
---
# <a name="sqltableprivileges"></a><span data-ttu-id="368b3-102">SQLTablePrivileges</span><span class="sxs-lookup"><span data-stu-id="368b3-102">SQLTablePrivileges</span></span>
  <span data-ttu-id="368b3-103">**SQLTablePrivileges** se puede ejecutar en un cursor estático.</span><span class="sxs-lookup"><span data-stu-id="368b3-103">**SQLTablePrivileges** can be executed on a static cursor.</span></span> <span data-ttu-id="368b3-104">Un intento de ejecutar **SQLTablePrivileges** en un control actualizable (controlado por conjunto de claves o dinámico) devuelve SQL_SUCCESS_WITH_INFO que indica que se ha cambiado el tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="368b3-104">An attempt to execute **SQLTablePrivileges** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="368b3-105">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client permite notificar información de tablas en servidores vinculados aceptando un nombre de dos partes para el parámetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="368b3-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="368b3-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="368b3-106">See Also</span></span>  
 <span data-ttu-id="368b3-107">[SQLTablePrivileges función] (https://go.microsoft.com/fwlink/?LinkId=59373\)</span><span class="sxs-lookup"><span data-stu-id="368b3-107">[SQLTablePrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59373\)</span></span>   
 [<span data-ttu-id="368b3-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="368b3-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
