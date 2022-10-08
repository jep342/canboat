#
# (C) 2009-2021, Kees Verruijt, Harlingen, The Netherlands.
#  
# This file is part of CANboat.
# 
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
# 
#     http://www.apache.org/licenses/LICENSE-2.0
# 
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# 

PLATFORM=$(shell uname | tr '[A-Z]' '[a-z]')-$(shell uname -m)
TARGETDIR=../../rel/$(PLATFORM)
ANALYZER=$(TARGETDIR)/analyzer
TEMPDIR=/tmp

.PHONY: test1 test2 tests

test1:	$(ANALYZER) recombine-frames.in recombine-frames.out
	$(ANALYZER) < recombine-frames.in > $(TEMPDIR)/recombine-frames.out -debug -q -fixtime recombine 2> $(TEMPDIR)/recombine-frames.err
	diff $(TEMPDIR)/recombine-frames.out recombine-frames.out
	diff $(TEMPDIR)/recombine-frames.err recombine-frames.err

test2:	$(ANALYZER) switch-multi-to-one-line.in switch-multi-to-one-line.out
	$(ANALYZER) < switch-multi-to-one-line.in > $(TEMPDIR)/switch-multi-to-one-line.out -debug -q -fixtime switch-multi-to-one-line 2> $(TEMPDIR)/switch-multi-to-one-line.err
	diff $(TEMPDIR)/switch-multi-to-one-line.out switch-multi-to-one-line.out
	diff $(TEMPDIR)/switch-multi-to-one-line.err switch-multi-to-one-line.err

tests:	test1 test2