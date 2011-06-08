
Natural language
----------------

GWT?

    Given
      [I'm hungry]
    When
      [I eat]
    Then
      [I feel better]

looks like Finite State Machine

    Initial State + Event => New State


    Given
      [I'm hungry]
    When
      [I drink]
    Then
      [I do not feel better]


[cuke]()

Two fold

* behavior in plain text using "natural" language

  parsed by [gherkin]()
      * [ragel]() based compiler

* each GWT sentence MUST have its implementation


Code
====

[rspec]()

    describe "hungry man" do
      let(:hungry) {Human.new(hungry: true)}
      it "should feel better after eating something" do
        hungry.eat!.should be_feel_better
      end
    end

[steak](https://github.com/cavalle/steak)
-----------------------------------------

!https://d3nwyuy0nl342s.cloudfront.net/img/5ff2a1af65e1d7b137f64640e90e3084499292b7/687474703a2f2f646c2e64726f70626f782e636f6d2f752f3634353332392f737465616b5f736d616c6c2e6a7067


Cavalle :

* An argument in favor of Cucumber I've never seen mentioned: Apparently clients and managers love it

    feature "Main page" do

       background do
         create_user :login => "jdoe"
         login_as "jdoe"
       end

       scenario "should show existing quotes" do
         create_quote :text => "The language of friendship is not words, but meanings",
                      :author => "Henry David Thoreau"

         visit "/"

         page.should have_css(".quote", :count => 1)
         within(:css, ".quote") do
           page.should have_css(".text", :text => "The language of friendship is not words, but meanings")
           page.should have_css(".author", :text => "Henry David Thoreau")
         end
       end

    end




