---
title: bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745281"
---
# <a name="bcp_columns"></a>bcp_columns
  Establece el número total de columnas del archivo de usuario para su uso con una copia masiva a o de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. [bcp_setbulkmode](bcp-setbulkmode.md) se puede utilizar en lugar de bcp_columns y [bcp_colfmt](bcp-colfmt.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *hdbc*  
 Es el identificador de la conexión ODBC habilitada para la copia masiva.  
  
 *nColumns*  
 Es el número total de columnas en el archivo de usuario. Incluso si está preparando la copia masiva de datos del archivo de usuario en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla y no pretende copiar todas las columnas del archivo de usuario, debe establecer *nColumns* en el número total de columnas de archivo de usuario.  
  
## <a name="returns"></a>Devoluciones  
 SUCCEED o FAIL.  
  
## <a name="remarks"></a>Observaciones  
 Solo se puede llamar a esta función después de que se haya llamado a [bcp_init](bcp-init.md) con un nombre de archivo válido.  
  
 Solo debe llamar a esta función si piensa utilizar un formato de archivo de usuario que difiere del valor predeterminado. Para obtener más información sobre una descripción del formato de archivo de usuario predeterminado, vea **bcp_init**.  
  
 Después de llamar a `bcp_columns` , debe llamar a [bcp_colfmt](bcp-colfmt.md)por cada columna del archivo de usuario para definir completamente un formato de archivo personalizado.  
  
## <a name="see-also"></a>Consulte también  
 [Bulk Copy Functions](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
