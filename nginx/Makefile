###############################################################################
# SELinux Reference Policy Module for Nginx on Debian
# 
# Copyright 2013 by Joe Johnston <joe@simple10.com>
# Copyright 2009 by Stuart Cianos <scianos@alphavida.com>
# 
# Licensed under GNU General Public License 3.0 or later. 
# Some rights reserved. See COPYING, AUTHORS.
# 
# @license GPL-3.0+ <http://spdx.org/licenses/GPL-3.0+>
###############################################################################

# installation paths
SHAREDIR := /usr/share/selinux

AWK ?= gawk
NAME ?= $(strip $(shell $(AWK) -F= '/^SELINUXTYPE/{ print $$2 }' /etc/selinux/config))

# Change to "-mcs" if MLS is not enabled
TYPE ?= $(NAME)-mls

HEADERDIR := $(SHAREDIR)/default/include
include $(HEADERDIR)/Makefile
