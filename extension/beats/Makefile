# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements. See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership. The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License. You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied. See the License for the
# specific language governing permissions and limitations
# under the License.

.PHONY: build

GOOS    := $(if $(GOOS),$(GOOS),$(shell go env GOOS))
GOARCH  := $(if $(GOARCH),$(GOARCH),$(shell go env GOARCH))
GOENV   := GOOS=$(GOOS) GOARCH=$(GOARCH)
GO      := $(GOENV) go

LDFLAGS := -w -s

default: build

build:
	$(GO) build -ldflags '$(LDFLAGS)' -o build/filebeat-$(GOOS)-$(GOARCH) filebeat/filebeat.go
	$(GO) build -ldflags '$(LDFLAGS)' -o build/metricbeat-$(GOOS)-$(GOARCH) metricbeat/metricbeat.go
	$(GO) build -ldflags '$(LDFLAGS)' -o build/winlogbeat-$(GOOS)-$(GOARCH) winlogbeat/winlogbeat.go
	$(GO) build -ldflags '$(LDFLAGS)' -o build/packetbeat-$(GOOS)-$(GOARCH) packetbeat/packetbeat.go
	$(GO) build -ldflags '$(LDFLAGS)' -o build/auditbeat-$(GOOS)-$(GOARCH) auditbeat/auditbeat.go
	$(GO) build -ldflags '$(LDFLAGS)' -o build/heartbeat-$(GOOS)-$(GOARCH) heartbeat/heartbeat.go
