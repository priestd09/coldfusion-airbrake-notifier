# ColdFusion Airbrake Notifier

CF Airbrake Notifier if a simple CFC for handling errors and exceptions from ColdFusion and sending them to [Airbrake](http://www.airbrake.io/); it uses v2 of the [Airbrake API](http://help.airbrake.io/faqs/api-2/notifier-api-v2).  CF Airbrake Notifier requires ColdFusion 8+.

## Example Usage

    <!--- Application.cfc --->
    <cfcomponent>
        <cffunction name="onApplicationStart">
            <cfset application.notifier = createobject("component", "AirbrakeNotifier").init(API_KEY)>
        </cffunction>
        <cffunction name="onError">
            <cfargument name="exception">
            <cfset application.notifier.send(arguments.exception)>
        </cffunction>
    </cfcomponent>

## Replacement for coldfusion-airbrake-notifier

This is a completely rewritten-from-scratch, drop-in replacement for [Shayne Sweeney](
https://github.com/shayne)'s [coldfusion-airbrake-notifier](http://github.com/shayne/coldfusion-airbrake-notifier) that works with v2 of the Airbrake API.

## Licensing and Attribution

This project is released under the MIT license as detailed in the LICENSE file that should be distributed with this library; the source code is [freely available](http://github.com/timblair/coldfusion-airbrake-notifier).

This project was developed by [Tim Blair](http://tim.bla.ir/) during work on [White Label Dating](http://www.whitelabeldating.com/), while employed by [Global Personals Ltd](http://www.globalpersonals.co.uk).  Global Personals Ltd have kindly agreed to the extraction and release of this software under the license terms above.
