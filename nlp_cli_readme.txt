USB connection to DLPC350 now open
Var Screen Info
 Display Width    = 912
 Display Height   = 1140
 Bits Per Pixel   = 32
 Pixel Clk        = 13333
 FrameBuffer size = 4158720
dlp_nirscan: invalid option -- 'h'
Usage: dlp_nirscan [-IvlSELdfGrTPfCpWRwxyAZN]
  -I Initialize DLPC350
  -v print dlp_nirscan application version information
  -l <num_images> load scan_img_000.bmp thru scan_img_nnn to memory from SD card for streaming
  -S <ptn_count> stream n images via parallel RGB that are preloaded using the -l option below
  -E <exposure_time_in_microseconds>
  -L number iterations to be performed in a loop; default is treated as 1
  -d delay in milli second between each iterations
  -f <file_name> to store the mean ADC readings
  -G Generate absorption spectrum for the reference and sample adc reading file list.
  -r <file_name> file with calibration scan mean  readings with no object (open beam)
  -T <threshold_factor> values in readings file that are below threshold_factor*median_of_readings will be discarded. Default threshold_factor is 0.001
  -P <sdf_file> prepare scan solution as per the given Scan Description File
  -f <file_name> to store the mean ADC readings
  -C perform calibration scan
  -p <file_name> find peaks in the data presented in <file_name>
  -W Write calibration info to EEPROM
  -R Restore calibration info from EEPROM
  -w Compute lambda-pixel and pixel-lambda polynomial co-efficients from peak_locations.txt
  -x Get DMD pixel positions for wavelengths given in wavelengths.txt
  -y get Wavelengths for pixel values given in pixels.txt
  -A <first pixel> input for generate_csv_patterns
  -Z <last pixel> input for generate_csv_patterns
  -N <num_patterns > input for generate_csv_patterns


 Example-1: ./dlp_nirscan -G -r<adc_read_file_ref> -f<adc_read_file> (Generates absorption file from the sample readings in <adc_read_file> and reference readings in <adc_read_file_ref>)
 Example-2: ./dlp_nirscan -A0 -Z1823 -N225 (Generates 225 patterns in CSV format with first patterns starting at pixel 0 and last one ending at pixel 1823)
 Example-3: ./dlp_nirscan -l10 -S245 -E1500 (Loads scan_img_000.bmp thru scan_img_009.bmp to memory and performs scan using 245 patterns from those images the exposure time of each pattern being 1500 microseconds


  **************** The following functions are under development and not fully qualified **************

  -g set Programmable Gain Amplifier Multiplier value
  -n <num_images> -B <firmware_file> - Rebuilds the given firmware file with scan_img_000.bmp thru scan_img_nnn.bmp
  -U <firmware_file> Uploads the specified firmware to DLPC350
  -i <first_img_index> -c <ptn_count> - Performs a scan using prebuilt scan images in flash starting at first_img_index and goes thru ptn_count 1-bit patterns
  -M <Measure flash load timing>  - Usage dlp_nirscan -i1 -c5 -M measure the load time for images 1 thru 6 and reports the timings
 Example-4: ./dlp_nirscan -i1 -C116 -E8000 (Performs scan with 116 patterns from flash starting with the image at index1 and exposure time of each pattern being 8000 microseconds)