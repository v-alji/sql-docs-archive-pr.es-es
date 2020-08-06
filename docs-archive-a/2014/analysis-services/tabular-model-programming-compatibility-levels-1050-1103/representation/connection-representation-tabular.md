---
title: Representación de conexión (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 4b410b16-d36e-4185-bb20-922e66e5e2b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 60f3fdc10baf5dc3be9cd1b0ee6196d2a8da3d2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671226"
---
# <a name="connection-representation-tabular"></a><span data-ttu-id="9f08a-102">Representación de conexión (tabular)</span><span class="sxs-lookup"><span data-stu-id="9f08a-102">Connection Representation (Tabular)</span></span>
  <span data-ttu-id="9f08a-103">El objeto de conexión define el origen de datos que rellena el modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="9f08a-103">The connection object defines the source of the data that populates the tabular model.</span></span>  
  
## <a name="connection-representation"></a><span data-ttu-id="9f08a-104">Representación de conexión</span><span class="sxs-lookup"><span data-stu-id="9f08a-104">Connection Representation</span></span>  
 <span data-ttu-id="9f08a-105">La especificación del objeto de conexión sigue las reglas de los proveedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9f08a-105">The specification for the connection object follows the rules of OLE DB providers.</span></span>  
  
### <a name="connection-in-amo"></a><span data-ttu-id="9f08a-106">Conexión en AMO</span><span class="sxs-lookup"><span data-stu-id="9f08a-106">Connection in AMO</span></span>  
 <span data-ttu-id="9f08a-107">Cuando se usa AMO para administrar una base de datos de modelo tabular, el objeto <xref:Microsoft.AnalysisServices.DataSource> en AMO coincide de forma unívoca con el objeto lógico de conexión.</span><span class="sxs-lookup"><span data-stu-id="9f08a-107">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.DataSource> object in AMO matches one-to-one to the connection logical object.</span></span>  
  
 <span data-ttu-id="9f08a-108">En el fragmento de código siguiente se muestra cómo crear un objeto de conexión o un origen de datos de AMO en un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="9f08a-108">The following code snippet shows how to create an AMO data source, or Connection object in a tabular model.</span></span>  
  
```  
  
//Create an OLEDB connection string  
StringBuilder SqlCnxStr = new StringBuilder();  
SqlCnxStr.Append(String.Format("Data Source={0};" ,SQLServer.Text));  
SqlCnxStr.Append(String.Format("Initial Catalog={0};", SQLDatabase.Text));  
SqlCnxStr.Append(String.Format("Persist Security Info={0};", false));  
SqlCnxStr.Append(String.Format("Integrated Security={0};", "SSPI"));  
SqlCnxStr.Append(String.Format("Provider={0}", "SQLNCLI11"));  
String DatasourceCnxString = SqlCnxStr.ToString();  
  
//Verify connection string and connectivity  
System.Data.OleDb.OleDbConnection OleDbCnx = new System.Data.OleDb.OleDbConnection(DatasourceCnxString);  
try  
{  
    OleDbCnx.Open();  
}  
catch ()  
{  
    throw;  
}  
String newDataSourceName = (string.IsNullOrEmpty(DataSourceName.Text) || string.IsNullOrWhiteSpace(DataSourceName.Text)) ? SQLDatabase.Text : DataSourceName.Text;  
AMO.DataSource newDatasource = newDatabase.DataSources.Add(newDataSourceName, newDataSourceName);  
newDatasource.ConnectionString = DatasourceCnxString.Text;  
if (impersonateServiceAccount.Checked)  
    newDatasource.ImpersonationInfo = new AMO.ImpersonationInfo(AMO.ImpersonationMode.ImpersonateServiceAccount);  
else  
{  
    if (String.IsNullOrEmpty(impersonateAccountUserName.Text))  
    {  
        MessageBox.Show(String.Format("Account User Name cannot be blank when using 'ImpersonateAccount' mode"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        return;  
    }  
    newDatasource.ImpersonationInfo = new AMO.ImpersonationInfo(AMO.ImpersonationMode.ImpersonateAccount, impersonateAccountUserName.Text, impersonateAccountPassword.Text);  
}  
newDatasource.Update();  
  
```  
  
## <a name="tabular-amo-2012-sample"></a><span data-ttu-id="9f08a-109">Ejemplo de AMO 2012 tabular</span><span class="sxs-lookup"><span data-stu-id="9f08a-109">Tabular AMO 2012 sample</span></span>  
 <span data-ttu-id="9f08a-110">Para comprender mejor cómo se usa AMO para crear y manipular representaciones de conexión, vea el código fuente del ejemplo AMO 2012 tabular; en concreto, examine el siguiente archivo de código fuente: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="9f08a-110">To have a better understanding on how to use AMO to create and manipulate connection representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="9f08a-111">El ejemplo está disponible en Codeplex.</span><span class="sxs-lookup"><span data-stu-id="9f08a-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="9f08a-112">El código de ejemplo se proporciona únicamente como apoyo a los conceptos lógicos explicados aquí y no se debe usar en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="9f08a-112">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
