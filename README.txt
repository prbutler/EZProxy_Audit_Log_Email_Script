# EZProxy_Audit_Log_Email_Script
# Description: A Perl script that processes the previous day's EZProxy audit log and  
#			   generates an email with interesting information.
#
# Software Requirements: Blat, Perl (Tested with Perl v5.8.8), and Windows OS. (This script 
# was written, tested, and is deployed in a Windows server environment. It may work with 
# other OS with some tweaks, but I cannot offer any guarantees.) 
#						 
#
# Inputs: 
#	- previous day's EZProxy audit log from EZProxy server. Format example: 20141028.txt
#	- Geographic location files GeoLiteCity-Location.csv and GeoLiteCity-Blocks.csv located at:
#	  http://geolite.maxmind.com/download/geoip/database/GeoLiteCity_CSV/GeoLiteCity-latest.zip. 
#	  Unzip the file and place the CSV files in the same directory as the GeoLiteCity.dat file
#	  that is used with EZProxy.
#	  This file should be updated monthly when you update the GeoLiteCity.dat file. 
#	- user_watchlist.txt - A locally maintained text file that contains usernames for the script to look 
#	  for and report on. One username per line, comments and blank lines are allowed in the file.
#	- ip_watchlist.txt - A locally maintained text file that contains IP addresses for the script to look 
#	  for and report on. One IP address per line, comments and blank lines are allowed in the file.
#		
# Outputs: A text file, audit_log_email.txt, that has collected interesting information from the 
# audit log, that will then be emailed to whomever you wish using Blat.
#
# NOTE: In order for this script to run, 12 variables with the value "CHANGE_ME" must be updated to match your local 
#		environment. This mostly has to do with path names and access to files, but also local variables. 
#		Examples are provided. Search this script to locate locate them all. 
#
# Written by Paul Butler, Ball State University Libraries, prbutler@bsu.edu. Caveat emptor!
