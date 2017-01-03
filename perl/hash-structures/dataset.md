 The dataset structure is basically as hashref that requires the following 
 
 ```
 
 my %inp=(
    'request' => {
      'table' => 'dataset_name',
      'transformation' => 'type_of_transformation',
      'messages' => 'on or off',
      'filter' => {
        'filtertype' => 'filtervalue',
      },
    }
  );

```
