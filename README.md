# cpanel-plan-to-cwp
Import hosting plan from cPanel into CentOS Web Panel

This BASH script will read package values stored in file and import them to CWP database table.

## Usage

`# bash cpanel-plan-to-cwp /path/to/packages/dir/reseller1_* /path/to/packages/dir/reseller2_*`

The package name is fetched from the basename. For example, if the given path to file is `/migration/cpanel_packages/besthost_kinder_10GB`, then

>  Package Name = besthost_kinder_10GB
>
>  Reseller Name = besthost
  
the correspoding SQL querey will be:

>`INSERT packages VALUES ('3', 'besthost_kinder_10GB', '500', '300', '0', '10', '0', '2', '0', '0', '0', '', 'besthost', '');`
 
The script can import package file name that contain white-space too.

The packages are stored in cPanel server at /var/cpanel/packages. You can copy required package files to the CWP server.
