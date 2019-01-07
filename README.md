# Codeigniter-SSP-datatables
library for SSP datatables serverside

##Getting Started
Follow the instruction before you use the library. This library reference https://datatables.net/manual/server-side

##Installing
Download Library Codeigniter SSP datatables

public function yourfunctioncallajax()
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

  if (isset($_POST['start'])) 
  {
    echo json_encode(
        Datatables_ssp::simple( $_POST, $table, $primaryKey, $columns )
    );
  }else{
    echo json_encode(
        Datatables_ssp::simple( $_GET, $table, $primaryKey, $columns )
    );
  }
}
