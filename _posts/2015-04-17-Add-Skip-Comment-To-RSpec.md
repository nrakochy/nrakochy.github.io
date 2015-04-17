---
layout:     post
title:      Add Comment to Pending Skip Statement in Rspec
date:       2015-04-17 12:00:00
summary:    How can I add a reason for skipping a test in Rspec?
categories: Rspec pending
---

How can I add a reason for skipping a test in Rspec? If you using `xit` or `skip` when
running your specs, you may have noticed the line:


    Pending: (Failures listed here are expected and do not affect your suite's status)

      1) ClassName#methodname returns a wonderful data set
         # No reason given
         # ./spec/services/class_name_spec.rb:48

In order to add a comment, you should use the `skip` syntax:

    it "returns a wonderful data set", :skip => "Great reason that I skipped this test" do
        expect(regular_test_suite_run).to eq(data)
    end

Or this

    it "returns a wonderful data set" do
        skip "Great reason that I skipped this test"
        expect(regular_test_suite_run).to eq(data)
    end

This will add your reason to the pending spec:

    1) ClassName#methodname returns a wonderful data set
       # Great reason that I skipped this test
       # ./spec/services/class_name_spec.rb:48







