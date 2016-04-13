---
id: 17
title: Bash Output Library
date: 2010-11-30T06:11:41+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=17
permalink: /bash-output-library/
categories:
  - Programming
tags:
  - bash
  - linux
  - script
---
Scripting allows for the automation of repetitive tasks in a consistent manner. When the number of scripts one has grows, it becomes necessary to start consolidating common elements. One such element is output. How messages are printed to the screen. The following is a small library built to print completion and error messages to the screen. Messages will print on the left and a status indicator will print on the right. The color codes were snagged from somewhere and the style will be familiar to those who have used [Gentoo Linux](http://www.gentoo.org/ "Homepage for Gentoo Linux"). Simply source this file into any existing script and call the functions as needed.

<pre># Output library
#
# Purpose: Format and color status messages
#
# Author: Erik Musick
#
# Syntax: function 

# Control characters
CBRK=$'\x1b[0;01m'  # Line break?
CNRM=$'\x1b[0;0m'   # Clear color
CUDL=$'\x1B[4m'     # Underline
CFSH=$'\x1B[5m'     # Flash
CRVS=$'\x1B[7m'     # Reverse video

# Normal color
CBLK=$'\x1B[0;30m'
CRED=$'\x1b[0;31m'
CGRN=$'\x1b[0;32m'
CYEL=$'\x1b[0;33m'
CBLU=$'\x1b[0;34m'
CMAG=$'\x1b[0;35m'
CCYN=$'\x1b[0;36m'
CWHT=$'\x1B[0;37m'

# Bright color
BBLK=$'\x1B[1;30m'
BRED=$'\x1b[1;31m'
BGRN=$'\x1b[1;32m'
BYEL=$'\x1b[1;33m'
BBLU=$'\x1b[1;34m'
BMAG=$'\x1b[1;35m'
BCYN=$'\x1b[1;36m'
BWHT=$'\x1B[1;37m'

# Background colors
BKBLK=$'\x1B[40m'
BKRED=$'\x1b[41m'
BKGRN=$'\x1b[42m'
BKYEL=$'\x1b[43m'
BKBLU=$'\x1b[44m'
BKMAG=$'\x1b[45m'
BKCYN=$'\x1b[46m'
BKWHT=$'\x1B[47m'

# "msg [OK]"
function pr_succ {
    local TWIDTH=$(tput cols)                           # Get terminal width
    local SWIDTH="$@"                                   # Save string
    local WSPACE="`expr ${TWIDTH} - ${#SWIDTH} + 21`"   # Amount of whitespace
    echo -n ${@}                                        # Print message
    printf "%${WSPACE}s" "${BBLU}[${BGRN}OK${BBLU}]"    # Pad with spaces
    echo "${CNRM}"                                      # Reset color with \n
}

# "msg [!!]"
function pr_fail {
    local TWIDTH=$(tput cols)                           # Get terminal width
    local SWIDTH="$@"                                   # Save string
    local WSPACE="`expr ${TWIDTH} - ${#SWIDTH} + 21`"   # Amount of whitespace
    echo -n ${@}                                        # Print message
    printf "%${WSPACE}s" "${BBLU}[${BRED}!!${BBLU}]"    # Pad with spaces
    echo "${CNRM}"                                      # Reset color with \n
}

# Warning msg in yellow
function pr_warn {
    echo -e "${BYEL}${@}${CNRM}"
}

# Information msg in blue
function pr_info {
    echo -e "${BBLU}${@}${CNRM}"
}

# Successful completion msg in green
function pr_done {
    echo -e "${BGRN}${@}${CNRM}"
}

# Error msg in red
function pr_err {
    echo -e "${BRED}${@}${CNRM}"
}</pre>