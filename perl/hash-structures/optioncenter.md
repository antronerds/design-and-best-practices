~~~~

%OptionCenter=(
	'site'=> {
		'cookies'=>{
			#key / vals from $ENV{'HTTP_COOKIE'}
			#'UID' => $sessionid if not yet specified 
		},
		'cookies_in_db' => {#cookie_process
			#key / vals
		}
	},
	'db_handles'=>{#ConnectGenomeDB = preferred over dbh_tview
		database => 'handle string'
	},
	'core'=> {
		#show table status r2base.pl
		#to access last updates on tables etc
		'records'=>'count of the number of tables',
		'data'=>{
			#for each table => {columns => value}
		}
	},
	'core_tview' => {#gbv2.pl ConnectChIPDB
		'records'=>'count',
		'data'=>{data=>data},
	},
	'community'=>{
		'admin' => {
			#foreach usergroup that the user is admin of
			usergroup => 1,
		},
		'invitations' => {
			#for each invited usergroup
			usergroup => 1,
		},
		'usergroups' => {
			#for each usergroup
			usergroup => {
				'tracks'=>'D/U/C',
				'genecategory'=> 'D/U/C'
			}
		},
		'usergroupstring'=> ', separated string of all usergroups a user is a member of',#for easy queries
	},
	'graph'=> {
		'button'=> {
			'hover_button1'=>{
				'pressed' => 'true/false',
				'count' => 'number',
			}
		}
	},
	'HugoOnce'=>{
		#each
		table =>'Checked/'
	},
	'main'=>{
		'genomebuild'=> 'genomebuild',#regionviewer.pl OverlapCounter_masked 
		'access' => {
			'open_access' => 'true/false',
			'logging_in'  => 'true/false',
			'rejection' => 'wrong_up/ip_anomaly/session_anomaly/logged_out/inactive', #security.pl
			'global_favoutite' => 'favourite dataset',
			'modules'=>{
				#forach module
				module => 'granted/',
			}
		},
		'usersettings'=> {
			'species'=> 'hs',#
			# setting / value (select username,setting,value from usersettings where username=?) security.pl 
		},
		'plugin'=>{#menuitems Not fully implemented. only initiated some time ago
			'menuitems'=>{label=>''},
		},
		'operation'=>{#gbrowser.pl gbrowserview
			'orientationmode'=>'tis/',
		},
		'species' => '',
		'cohort'=>{
			'id'=> 'cohort_id',
			'id_string'=>'string',
			'sample_id_string'=> 'string',
			'pat_id_string'=> 'string',
		},
		'dbh_tview' => {
			'handle' => 'dbi_string',
			'tables' => {
				#foreach table in the other server
				table => 1,
			}
		},
		#bit ugly but is being used like this (please use ConnectGenomeDB in stead)
		'dbh_'.genomebuild=>{			
		},
		'platforms'=>{#DataSetter
			#each table / chiptype
			chiptype=>{table=>1}
		},
		'TableLister'=>{
			#each table
			group=>{table=>1}
		},
		'database'=> {
			#foreach table and field in the datasetinfo
			field =>{table=>value},
			
			'line_termination'=> " lines terminated by '\\r\\n'", #core/dbcore.pl #Creating core tables
			'timeseries' => { #continue.pl DataSetter
				timeseriestable =>{
					'type'=> 'free/access'
				}
			},
			'timeseries_species' => {
				#foreach timeseries table
				timeseriestable => 'the species'
			},
			'tables' => {
				#foreach table in the database
				table=>"Y",
			},
			'datasets'=> { #continue.pl DataSetter
				#foreach dataset
				dataset => {
					'type' => 'free/ext/restricted/',
					'kaplan'=> 'true/false',
					'showname' => '',
					'showname_l1' => '',
					'showname_l2' => '',					
					'showname_concise' => '',
					'showname_concise_t' => '',
				},
			},
			'groupnames'=>{
				#groupname / 
			},
			'groupnames_in' => 'in string for in mysql',
			'surv_data_base' => {#basedataset based
				basedataset => 'yes/no'
			},
			'surv_data' => {#Table based
				table => 'yes/no'
			},
			'chipinfo' => { #db_chiptype data
				value => chiptype,
			},
			'specific_access' =>{
				#each table to which a user has specific access
				table
			},
		},
		'db_hugoonce' =>{
			#each table
			table => {'hugoonce'=>hugoonce, 'datestamp'=> datestamp, 'annot_datestamp'=> annot_datestamp},
		},
		#javascript slot should be phased out
		'javascript'=> {
			'messageboxes'=>'loaded'
		},
		'styles'=>{
			labels => 1
		}
	},
	'SurvivalData_ext' =>{#GetSurvivalData
	
	},
	'SurvivalData'=>{#GetSurvivalData
	
	},
	'gbv2'=>{
		'track_global'=>{
			'samplelist'=>{
				#each
				sample_id=>1
			},
			'sample_labels'=>{
				#each
				sample_id=>1			
			}
		}
	},
	'prep_query' => {
		"DWGI" =>{ #DecorateWithGeneInfo
			#geneid, symbol,
		},
		'id_conv_p2g'=>{#idconv_probeset2genesymbol
			
		}
	},
	'temp'=>{
		'datasetlister'=>{'user'=>'','group'=>''}
	},
	'tracklister2'=>"Loaded",#tracks.pl tracklister2 and tracklister3
	'CatChoose'=>{#genesetsubs.pl CategoryChooserV2
		'stats'=>{'jsgen'=>1}
	},
	'exporters'=>{
		'exporter_tmev'=>1,#exporters/exporter_tmev.pl
		'exporter_tmev_ts'=>1,#exporters/exporter_tmev_ts.pl
	},
);

~~~~
