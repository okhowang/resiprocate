# $Id$

EXTRA_DIST = ReadMe.txt
EXTRA_DIST += *.vcxproj

SUBDIRS = .
SUBDIRS += dtls_wrapper/test

#AM_CXXFLAGS = -DUSE_ARES
AM_CXXFLAGS = -I $(top_srcdir)

lib_LTLIBRARIES = libreflow.la
libreflow_la_LIBADD = ../reTurn/client/libreTurnClient.la
libreflow_la_LIBADD += ../rutil/librutil.la
if USE_SIPXTAPI
libreflow_la_LIBADD += -lsipXmediaProcessing
endif
if USE_SRTP1
libreflow_la_LIBADD += @LIBSSL_LIBADD@ -lsrtp
else
libreflow_la_LIBADD += @LIBSSL_LIBADD@ -lsrtp2
endif
libreflow_la_LIBADD += @LIBSTL_LIBADD@
libreflow_la_LIBADD += @LIBPTHREAD_LIBADD@
libreflow_la_LDFLAGS = @LIBTOOL_VERSION_RELEASE@ -export-dynamic

libreflow_la_SOURCES = FakeSelectSocketDescriptor.cxx \
        Flow.cxx \
        FlowDtlsSocketContext.cxx \
        FlowDtlsTimerContext.cxx \
        FlowManager.cxx \
        FlowManagerSubsystem.cxx \
	HEPRTCPEventLoggingHandler.cxx \
        MediaStream.cxx \
        dtls_wrapper/DtlsTimer.cxx \
        dtls_wrapper/DtlsSocket.cxx \
        dtls_wrapper/DtlsFactory.cxx \
        dtls_wrapper/bf_dwrap.cxx

reflowincludedir = $(includedir)/reflow
nobase_reflowinclude_HEADERS = ErrorCode.hxx \
	FakeSelectSocketDescriptor.hxx \
	FlowDtlsSocketContext.hxx \
	FlowDtlsTimerContext.hxx \
	Flow.hxx \
	FlowContext.hxx \
	FlowManagerException.hxx \
	FlowManager.hxx \
	FlowManagerSubsystem.hxx \
	HEPRTCPEventLoggingHandler.hxx \
	MediaStream.hxx \
	RTCPEventLoggingHandler.hxx \
	Srtp2Helper.hxx \
	dtls_wrapper/bf_dwrap.hxx \
	dtls_wrapper/DtlsFactory.hxx \
	dtls_wrapper/DtlsSocket.hxx \
	dtls_wrapper/DtlsTimer.hxx

##############################################################################
# 
# The Vovida Software License, Version 1.0 
# Copyright (c) 2000-2007 Vovida Networks, Inc.  All rights reserved.
# 
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
# 
# 1. Redistributions of source code must retain the above copyright
#    notice, this list of conditions and the following disclaimer.
# 
# 2. Redistributions in binary form must reproduce the above copyright
#    notice, this list of conditions and the following disclaimer in
#    the documentation and/or other materials provided with the
#    distribution.
# 
# 3. The names "VOCAL", "Vovida Open Communication Application Library",
#    and "Vovida Open Communication Application Library (VOCAL)" must
#    not be used to endorse or promote products derived from this
#    software without prior written permission. For written
#    permission, please contact vocal@vovida.org.
# 
# 4. Products derived from this software may not be called "VOCAL", nor
#    may "VOCAL" appear in their name, without prior written
#    permission of Vovida Networks, Inc.
# 
# THIS SOFTWARE IS PROVIDED "AS IS" AND ANY EXPRESSED OR IMPLIED
# WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES
# OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE AND
# NON-INFRINGEMENT ARE DISCLAIMED.  IN NO EVENT SHALL VOVIDA
# NETWORKS, INC. OR ITS CONTRIBUTORS BE LIABLE FOR ANY DIRECT DAMAGES
# IN EXCESS OF $1,000, NOR FOR ANY INDIRECT, INCIDENTAL, SPECIAL,
# EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
# PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
# PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY
# OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE
# USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH
# DAMAGE.
# 
# ====================================================================
# 
# This software consists of voluntary contributions made by Vovida
# Networks, Inc. and many individuals on behalf of Vovida Networks,
# Inc.  For more information on Vovida Networks, Inc., please see
# <http://www.vovida.org/>.
# 
##############################################################################
