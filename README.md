# Codeigniter-SSP-datatables
library for SSP datatables serverside.

## Getting Started
Follow the instruction before you use the library. This library reference https://datatables.net/manual/server-side.
we only change a little code, so we can use the codeigniter database. 

## Installing
Download Library Codeigniter SSP datatable, put on library folder.

function to call ajax from client :

```php
function yourfunctioncallajax()
{
  $this->load->library('Datatables_ssp');
  $primaryKey = 'thisyourprimarykey';

  $table = 'yourtable';
  //(ex. field)
  $columns = array(
      array( 'db' => 'item', 'dt' => 0 ),
      array( 'db' => 'item_in', 'dt' => 1 ),
      array( 'db' => 'item_out', 'dt' => 2 ),
      array( 'db' => 'item_total', 'dt' => 3 )
  );

  // $conn use by default if you naming another select your active connection
  if (isset($_POST['start'])) 
  {
    echo json_encode(
        Datatables_ssp::simple( $_POST, $table, $primaryKey, $columns, $conn )
    );
  }else{
    echo json_encode(
        Datatables_ssp::simple( $_GET, $table, $primaryKey, $columns, $conn )
    );
  }
}
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. If you want to make it more dynamic, your contribution really helps others.
