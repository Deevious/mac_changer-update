#!/usr/bin/env python

import subprocess
import optparse

# Handles user-input using args.
parser = optparse.OptionParser()

# Assigning user options to parser.
parser.add_option("-i", "--interface", dest="interface", help="Interface to change its MAC address")
parser.add_option("-m", "--mac", dest="new_mac", help="New MAC address")

# Returns args and values.
(options, arguments) = parser.parse_args()

# User input + options.
interface = options.interface
new_mac = options.new_mac
print("[+] Changing MAC address for " + interface + " to " + new_mac)

# Using .call to execute system commands.
# Executes 'ifconfig' + disables interface.
subprocess.call(["ifconfig", interface, "down"])

# Renaming MAC address.
subprocess.call(["ifconfig", interface, "hw", "ether", new_mac])

# Enabling MAC address.
subprocess.call(["ifconfig", interface, "up"])
