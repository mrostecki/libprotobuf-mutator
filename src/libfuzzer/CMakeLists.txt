# Copyright 2017 Google Inc. All rights reserved.
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

add_library(protobuf-mutator-libfuzzer
            libfuzzer_mutator.cc
            libfuzzer_macro.cc)
target_link_libraries(protobuf-mutator-libfuzzer
                      protobuf-mutator
                      ${PROTOBUF_LIBRARIES})
set_property(TARGET protobuf-mutator-libfuzzer
             PROPERTY COMPILE_FLAGS "${NO_FUZZING_FLAGS}")

install(TARGETS protobuf-mutator-libfuzzer ARCHIVE DESTINATION ${LIB_DIR})
