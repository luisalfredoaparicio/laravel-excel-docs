# Storing exports on disk

[[toc]]

Exports can easily be stored on any [filesystem](https://laravel.com/docs/master/filesystem) that Laravel supports.


## Default disk

```php
public function storeExcel() 
{
    // Store on default disk
    Excel::store(new InvoicesExport(2018), 'invoices.xlsx');
}
```

## Custom disks

```php
public function storeExcel() 
{
    // Store on a different disk (e.g. s3)
    Excel::store(new InvoicesExport(2018), 'invoices.xlsx', 's3');
    
    // Store on a different disk with a defined writer type. 
    Excel::store(new InvoicesExport(2018), 'invoices.xlsx', 's3', Excel::XLSX);
}
```

