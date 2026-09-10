(ns association.facts-test
  (:require [clojure.test :refer [deftest is]]
            [association.facts :as facts]))

(deftest andi-has-spec-basis
  (let [sb (facts/spec-basis "andi")]
    (is (= 2 (count sb)))
    (is (every? #(= "9411" (:association-rule/isic %)) sb))
    (is (every? #(= "COL" (:association-rule/country %)) sb))))

(deftest unknown-association-has-no-spec-basis
  (is (nil? (facts/spec-basis "ibec")))
  (is (nil? (facts/spec-basis "zzz"))))

(deftest coverage-is-honest
  (let [c (facts/coverage ["andi" "ibec"])]
    (is (= 2 (:requested c)))
    (is (= 1 (:covered c)))
    (is (= ["ibec"] (:missing-associations c)))))

(deftest by-topic-filters
  (is (= 2 (count (facts/by-topic "andi" :governance))))
  (is (empty? (facts/by-topic "andi" :labor)))
  (is (empty? (facts/by-topic "ibec" :governance))))
