#
#    Copyright 2019 EPAM Systems
#
#    Licensed under the Apache License, Version 2.0 (the "License");
#    you may not use this file except in compliance with the License.
#    You may obtain a copy of the License at
#
#       http://www.apache.org/licenses/LICENSE-2.0
#
#    Unless required by applicable law or agreed to in writing, software
#    distributed under the License is distributed on an "AS IS" BASIS,
#    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#    See the License for the specific language governing permissions and
#    limitations under the License.
#

FROM python:3.6

ENV LANG=C.UTF-8 LC_ALL=C.UTF-8
ENV PATH /opt/conda/bin:$PATH

# Install native dependencies
RUN apt-get update --fix-missing && \
    apt-get install -y wget bzip2 ca-certificates curl git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install legionctl
RUN pip install six
RUN pip install -e 'git+https://github.com/legion-platform/legion.git@1.0.0-rc18#egg=legion-sdk&subdirectory=legion/sdk'
RUN pip install -e 'git+https://github.com/legion-platform/legion.git@1.0.0-rc18#egg=legion-cli&subdirectory=legion/cli'

#RUN legionctl --version

CMD [ "/bin/bash" ]
