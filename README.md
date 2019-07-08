# nagios-plugins

A collection of check plugins for Nagios, check_mk ...


## check_mk local agent plugins (/check_mk-local/)

### Prerequisites

- Perl Interpreter
- `nut_ups` :: Configured [Network UPS Tools](http://www.networkupstools.org)

### Installation

Copy the file(s) to your local agent plugin directory, e.g. `/usr/lib/check_mk_agent/local`

Some settings can be configured in the plugin files (section SETTINGS).


## Classic Nagios plugins (/nagios-classic/)

### Prerequisites

- Perl Interpreter
- Monitoring::Plugin / Nagios::Plugin and other Perl modules (install via packet manager or CPAN)


### Installation

Copy the scripts into your favourite directory and try them out by calling the script directly from command line, e.g.

    gege@box:/opt/git/nagios-plugins> ./check_qnap_hdd -H 10.0.1.10 -w 40 -c 45
	QNAP HDDs OK - HDD1: 21C, HDD2: 20C | 'HDD1 Temp'=21;40;45 'HDD2 Temp'=20;40;45

For the integration in your monitoring system read the corresponding manuals.

*These checks can be used with check_mk via "Host & Service Parameters" -> Active checks -> Classical active and passive Monitoring checks*

### Usage

#### Travis CI Plugin

- `check_travis_status -r <repository-user/-name> [-t timeout]` :: Check Travis CI build status for repository

Repository format: `user/name` (e.g. `dev-sec/puppet-os-hardening`)

#### QNAP NAS Plugins

- `check_qnap_hdd -H <host> -w <warning-temp> -c <critical-temp> [-t timeout]` :: Check harddisk temperature
- `check_qnap_temp -H <host> -w <warning-temp> -c <critical-temp> [-t timeout]` :: Check system temperature
- `check_qnap_volumes -H <host> -w <warning free space%> -c <critical free space%> [-t timeout]` :: Check free space on volume


## License and Author

* Author: Michael Geiger <info@mgeiger.de>

Licensed under the GNU General Public License, Version 3 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

    http://www.gnu.org/licenses/gpl-3.0.html

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
