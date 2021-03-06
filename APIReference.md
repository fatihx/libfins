# Libfins API Reference

Libfins is a library to communicate over the FINS/TCP protocol over ethernet with Omron PLCs. The library is written
in C and can be compiled with any modern C compiler. The API to the library is described in this document.

## Constants

* [PLC CPU modes](doc/fins_cpu_mode.md)
* [Default communication settings](doc/fins_default.md)
* [Bit force modes](doc/fins_force.md)
* [FINS user message masks](doc/fins_msg.md)
* [Data types](doc/fins_data_type.md)
* [Parameter areas](doc/fins_param_area.md)
* [Function return values](doc/fins_retval.md)

## Structures

* [`struct fins_cpustatus_tp;`](doc/fins_cpustatus_tp.md)
* [`struct fins_cycletime_tp;`](doc/fins_cycletime_tp.md)
* [`struct fins_multidata_tp;`](doc/fins_multidata_tp.md)
* [`struct fins_unitdata_tp;`](doc/fins_unitdata_tp.md)

## Functions

### Connection Functions

* [`finslib_disconnect( sys );`](doc/finslib_disconnect.md)
* [`finslib_tcp_connect( sys, address, port, local_net, local_node, local_unit, remote_net, remote_node, remote_unit, error_val, error_max );`](doc/finslib_tcp_connect.md)

### Data Read Functions

* [`finslib_memory_area_read_bcd16( sys, start, data, num_bcd16 );`](doc/finslib_memory_area_read_bcd16.md)
* [`finslib_memory_area_read_bcd32( sys, start, data, num_bcd32 );`](doc/finslib_memory_area_read_bcd32.md)
* [`finslib_memory_area_read_bit( sys, start, data, num_bit );`](doc/finslib_memory_area_read_bit.md)
* [`finslib_memory_area_read_int16( sys, start, data, num_int16 );`](doc/finslib_memory_area_read_int16.md)
* [`finslib_memory_area_read_int32( sys, start, data, num_int32 );`](doc/finslib_memory_area_read_int32.md)
* [`finslib_memory_area_read_sbcd16( sys, start, data, num_sbcd16, type );`](doc/finslib_memory_area_read_sbcd16.md)
* [`finslib_memory_area_read_sbcd32( sys, start, data, num_sbcd32, type );`](doc/finslib_memory_area_read_sbcd32.md)
* [`finslib_memory_area_read_uint16( sys, start, data, num_uint16 );`](doc/finslib_memory_area_read_uint16.md)
* [`finslib_memory_area_read_uint32( sys, start, data, num_uint32 );`](doc/finslib_memory_area_read_uint32.md)
* [`finslib_memory_area_read_word( sys, start, data, num_word );`](doc/finslib_memory_area_read_word.md)
* [`finslib_multiple_memory_area_read( sys, item, num_item );`](doc/finslib_multiple_memory_area_read.md)

### Data Write Functions

* [`finslib_forced_set_reset_cancel( sys );`](doc/finslib_forced_set_reset_cancel.md)
* [`finslib_memory_area_fill( sys, start, fill_data, num_word );`](doc/finslib_memory_area_fill.md)
* [`finslib_memory_area_transfer( sys, source, dest, num_words );`](doc/finslib_memory_area_transfer.md)
* [`finslib_memory_area_write_bcd16( sys, start, data, num_bcd16 );`](doc/finslib_memory_area_write_bcd16.md)
* [`finslib_memory_area_write_bcd32( sys, start, data, num_bcd32 );`](doc/finslib_memory_area_write_bcd32.md)
* [`finslib_memory_area_write_bit( sys, start, data, num_bit );`](doc/finslib_memory_area_write_bit.md)
* [`finslib_memory_area_write_int16( sys, start, data, num_int16 );`](doc/finslib_memory_area_write_int16.md)
* [`finslib_memory_area_write_int32( sys, start, data, num_int32 );`](doc/finslib_memory_area_write_int32.md)
* [`finslib_memory_area_write_sbcd16( sys, start, data, num_sbcd16, type );`](doc/finslib_memory_area_write_sbcd16.md)
* [`finslib_memory_area_write.sbcd32( sys, start, data, num_sbcd32, type );`](doc/finslib_memory_area_write_sbcd32.md)
* [`finslib_memory_area_write_uint16( sys, start, data, num_uint16 );`](doc/finslib_memory_area_write_uint16.md)
* [`finslib_memory_area_write_uint32( sys, start, data, num_uint32 );`](doc/finslib_memory_area_write_uint32.md)
* [`finslib_memory_area_write_word( sys, start, data, num_word );`](doc/finslib_memory_area_write_word.md)

### CPU Operation Functions

* [`finslib_clock_read( sys, datetime );`](doc/finslib_clock_read.md)
* [`finslib_clock_write( sys, datetime, do_sec, do_dow );`](doc/finslib_clock_write.md)
* [`finslib_connection_data_read( sta, unitdata, start_unit, num_units );`](doc/finslib_connection_data_read.md)
* [`finslib_cpu_unit_data_read( sys, cpudata );`](doc/finslib_cpu_unit_data_read.md)
* [`finslib_cpu_unit_status_read( sys, status );`](doc/finslib_cpu_unit_status_read.md)
* [`finslib_cycle_time_init( sys );`](doc/finslib_cycle_time_init.md)
* [`finslib_cycle_time_read( sys, ctime );`](doc/finslib_cycle_time_read.md)
* [`finslib_set_cpu_run( sys, do_monitor );`](doc/finslib_set_cpu_run.md)
* [`finslib_set_cpu_stop( sys );`](doc/finslib_set_cpu_stop.md)

### Parameter Area Functions

* [`finslib_parameter_area_clear( sys, area_code, num_words );`](doc/finslib_parameter_area_clear.md)
* [`finslib_parameter_area_read( sys, area_code, data_ start_word, num_words );`](doc/finslib_parameter_area_read.md)
* [`finslib_parameter_area_write( sys, area_code, data, start_word, num_words );`](doc/finslib_parameter_area_write.md)

### Program Area Functions

* [`finslib_program_area_clear( sys, do_interrupt_tasks );`](doc/finslib_program_area_clear.md)
* [`finslib_program_area_read( sys, data, start_word, num_bytes );`](doc/finslib_program_area_read.md)
* [`finslib_program_area_write( sys, data, start_word, num_bytes );`](doc/finslib_program_area_write.md)

### Access Functions

* [`finslib_access_log_read( sys, accessdata, start_record, num_records, stored_records );`](doc/finslib_access_log_read.md)
* [`finslib_access_right_acquire( sys, nodedata );`](doc/finslib_access_right_acquire.md)
* [`finslib_access_right_forced_acquire( sys );`](doc/finslib_access_right_forced_acquire.md)
* [`finslib_access_right_release( sys );`](doc/finslib_access_right_release.md)
* [`finslib_write_access_log_clear( sys );`](doc/finslib_write_access_log_clear.md)

### Error and Message Functions

* [`finslib_error_clear( sys, error_code );`](doc/finslib_error_clear.md)
* [`finslib_error_clear_all( sys );`](doc/finslib_error_clear_all.md)
* [`finslib_error_clear_current( sys );`](doc/finslib_error_clear_current.md)
* [`finslib_error_clear_fal( sys, fal_number );`](doc/finslib_error_clear_fal.md)
* [`finslib_error_clear_fals( sys, fals_number );`](doc/finslib_error_clear_fals.md)
* [`finslib_error_log_clear( sys );`](doc/finslib_error_log_clear.md)
* [`finslib_error_log_read( sys, errordata, start_record, num_records, stored_records );`](doc/finslib_error_log_read.md)
* [`finslib_message_clear( sys, msg_mask );`](doc/finslib_message_clear.md)
* [`finslib_message_fal_fals_read( sys, faldata, fal_number );`](doc/finslib_message_fal_fals_read.md)
* [`finslib_message_read( sys, msgdata, msg_mask );`](doc/finslib_message_read.md)

### File System Functions

* [`finslib_area_file_compare( sys, start, disk, path, file, num_records );`](doc/finslib_area_file_compare.md)
* [`finslib_area_to_file_transfer( sys, start, disk, path, file, num_records );`](doc/finslib_area_to_file_transfer.md)
* [`finslib_file_memory_format( sys, disk );`](doc/finslib_file_memory_format.md)
* [`finslib_file_name_read( sys, diskinfo, fileinfo, disk, path, start_file, num_files );`](doc/finslib_file_name_read.md)
* [`finslib_file_read( sys, disk, path, filename, data, file_position, num_bytes );`](doc/finslib_file_read.md)
* [`finslib_file_to_area_transfer( sys, start, disk, path, file, num_records);`](doc/finslib_file_to_area_transfer.md)
* [`finslib_file_write( sys, disk, path, filename, data, file_position, num_bytes, open_mode );`](doc/finslib_file_write.md)

### General Utility Functions

* [`finslib_bcd_to_int( value, type );`](doc/finslib_bcd_to_int.md)
* [`finslib_errmsg( error_code, buffer, buffer_len );`](doc/finslib_errmsg.md)
* [`finslib_filename_to_83( infile, outfile );`](doc/finslib_filename_to_83.md)
* [`finslib_int_to_bcd( value, type );`](doc/finslib_int_to_bcd.md)
* [`finslib_milli_second_sleep( int msec );`](doc/finslib_milli_second_sleep.md)
* [`finslib_monotonic_sec_timer( void );`](doc/finslib_monotonic_sec_timer.md)
* [`finslib_raw( sys, command, buffer, send_len, recv_len );`](doc/finslib_raw.md)
* [`finslib_valid_directory( path );`](doc/finslib_valid_directory.md)
* [`finslib_valid_filename( filename );`](doc/finslib_valid_filename.md)
