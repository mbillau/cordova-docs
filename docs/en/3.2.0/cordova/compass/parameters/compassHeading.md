---
 license: Licensed to the Apache Software Foundation (ASF) under one
         or more contributor license agreements.  See the NOTICE file
         distributed with this work for additional information
         regarding copyright ownership.  The ASF licenses this file
         to you under the Apache License, Version 2.0 (the
         "License"); you may not use this file except in compliance
         with the License.  You may obtain a copy of the License at

           http://www.apache.org/licenses/LICENSE-2.0

         Unless required by applicable law or agreed to in writing,
         software distributed under the License is distributed on an
         "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
         KIND, either express or implied.  See the License for the
         specific language governing permissions and limitations
         under the License.
---

# compassHeading

A `CompassHeading` object is returned to the `compassSuccess` callback function.

## Properties

- __magneticHeading__: The heading in degrees from 0-359.99 at a single moment in time. _(Number)_

- __trueHeading__: The heading relative to the geographic North Pole in degrees 0-359.99 at a single moment in time. A negative value indicates that the true heading can't be determined.  _(Number)_

- __headingAccuracy__: The deviation in degrees between the reported heading and the true heading. _(Number)_

- __timestamp__: The time at which this heading was determined.  _(milliseconds)_

## Description

The `CompassHeading` object is returned to the `compassSuccess` callback function.

## Amazon Fire OS Quirks

- `trueHeading` is not supported, but reports the same value as `magneticHeading`

- `headingAccuracy` is always 0 because there is no difference between the `magneticHeading` and `trueHeading`

## Android Quirks

- The `trueHeading` property is not supported, but reports the same value as `magneticHeading`.

- The `headingAccuracy` property is always 0 because there is no difference between the `magneticHeading` and `trueHeading`.

## iOS Quirks

- The `trueHeading` property is only returned for location services enabled via `navigator.geolocation.watchLocation()`.

- For iOS 4 devices and above, heading factors in the device's current orientation, and does not reference its absolute position, for apps that supports that orientation.
