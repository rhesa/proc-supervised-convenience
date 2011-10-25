Proc::Supervised::ConveUnsieerncCeo(n3t)ributed Perl DocPurmoecn:t:aStuipoenrvised::Convenience(3)



NNAAMMEE
       Proc::Supervised::Convenience - Supervise concurrent worker processes

SSYYNNOOPPSSIISS
       driver script:

         #!/usr/bin/perl

         use Proc::Supervised::Convenience;

         Proc::Supervised::Convenience
           ->new_with_options( program => \&work )
           ->supervise;

         sub work {
           my @args = @_;
           # code to run forever
         }

       invocation:

         ./work -d -j 10 foo bar

FFEEAATTUURREESS
       ·   auto-restarts worker processes

       ·   kill -HUP  to restart all workers

       ·   kill -INT  to stop

       ·   kill -USR1 to relaunch

CCoommmmaanndd--lliinnee ooppttiioonnss
       ·   --detach | -d       # detach from terminal

       ·   --processes | -j N  # run N copies of &work

       Any remaining command line arguments are passed on as is to your work
       subroutine.

SSEEEE AALLSSOO
       POE::Component::Supervisor.

CCOOPPYYRRIIGGHHTT && LLIICCEENNSSEE
       Copyright 2011 Rhesa Rozendaal, all rights reserved.

       This program is free software; you can redistribute it and/or modify it
       under the same terms as Perl itself.



perl v5.14.1                      2011-10-25  Proc::Supervised::Convenience(3)
