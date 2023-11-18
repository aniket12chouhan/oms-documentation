# Sync Customer
If the order contains a new customer not present in Netsuite, the system won't allow the order to be pushed. Therefore, it's vital to synchronize customer data from HotWax Commerce to Netsuite before order creation.

## Export customers from HotWax
Scheduled job in HotWax Commerce generates a CSV file comprising customers who have not been synchronized to Netsuite.

This job is scheduled in the integration layer and not executed natively in the OMS.

{% hint style="warning" %}
    To change this job's frequency, connect with the integration team.
{% endhint %}

**SFTP Location**

```
/home/{sftp-username}/netsuite/customer/export
```

### Import customers into NetSuite
Schedule the following SuiteScript to export a feed of recently created customers from NetSuite
```
HC_SC_ImportCustomer
```

### Export customer IDs from NetSuite
Schedule this SuiteScript to export a file of recently created customers in NetSuite.
```
HC_MR_ExportedCustomerCSV
```
Verify that the generated file is placed at this SFTP Location
```
/home/{sftp-username}/netsuite/customer/import/
```

### Import NetSuite Customer into HotWax
Enable this job in HotWax Commerce to consume the file generated by HotWax
```
Import Party Identification
FTP Config: IMP_PARTY_IDENT
```